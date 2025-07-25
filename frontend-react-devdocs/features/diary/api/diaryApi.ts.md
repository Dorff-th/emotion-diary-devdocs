# 📄 diaryApi.ts
# 📁 위치
features/diary/api/diaryApi.ts

---

# 🧭 역할
사용자 회고 목록 데이터를 서버에서 가져오기 위한 API 함수(fetchDiaryList)와 회고 관련 타입 정의(DiaryEntry, DiaryGroup, DiaryItemType)를 포함한 모듈입니다.

---

# 🔗 주요 import 목록
| 항목              | 설명            | 링크                                                         |
| --------------- | ------------- | ---------------------------------------------------------- |
| `axiosInstance` | 공통 Axios 인스턴스 | [axiosInstance.ts](../../../lib/axios/axiosInstance.ts.md) |


---

## 🧩 주요 export 목록
🔹 fetchDiaryList(page: number, size = 10)
지정된 페이지 번호와 크기(size)에 따라 서버에서 회고 목록을 가져옵니다.

내부적으로 /user/diaries API를 호출합니다.

반환 타입: Promise<DiaryListResponse>

---

```ts
const response = await axiosInstance.get<DiaryListResponse>(
  `/user/diaries?page=${page-1}&size=${size}`
);
```

🔸 DiaryItemType
```ts
export interface DiaryItemType {
  id: number;
  diaryDate: string;
  summary: string;
  emotion: string;
  habitTags: string[];
  feelingKo: string;
  feelingEn: string;
  content: string;
  gptFeedback: string;
  feedback: string;
}
```
예전 회고 형식을 포괄하는 타입으로 보이며, 현재 페이지에서는 사용되지 않을 수 있습니다.

🔸 DiaryEntry
```ts
export interface DiaryEntry {
  id: number;
  content: string;
  emotion: number;
  feedback: string;
  feelingKo: string;
  feelingEn: string;
  habitTags: string;
  createdAt: string;
}
```
실제 개별 회고 항목의 구조이며, DiaryListPage.tsx에서 사용됩니다.

🔸 DiaryGroup
```ts
export interface DiaryGroup {
  date: string;
  summary: string | null;
  entries: DiaryEntry[];
}
날짜별 회고 항목을 묶는 그룹 단위 구조입니다. summary는 해당 날짜의 GPT 요약이며, entries는 DiaryEntry[]로 구성됩니다.
```

🔸 DiaryListResponse
```ts
export interface DiaryListResponse {
  content: DiaryGroup[];
  totalPages: number;
  page: number;
}
```
페이징 정보를 포함한 회고 목록 응답 구조입니다. content에는 DiaryGroup[]이 포함됩니다.

---
📌 기타 참고
이 API는 Emotion-Diary App에서 회고 목록을 불러오는 핵심 기능이며, 페이지네이션 구현의 기반이 됩니다.

size 기본값은 10이며, 필요 시 인자로 조정 가능합니다.

page 인자는 1부터 시작하지만 API는 0-based이므로 내부에서 page - 1로 보정합니다.

