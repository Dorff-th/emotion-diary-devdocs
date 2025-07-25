# 📄 DiaryListPage.tsx
## 📁 위치
features/diary/pages/DiaryListPage.tsx

## 🧭 역할
사용자의 회고 목록을 날짜별로 그룹화하여 보여주는 페이지입니다. 각 날짜에는 GPT 요약이 함께 표시될 수 있으며, 상세 회고 항목은 펼침형으로 구성되어 있습니다. 페이지네이션 기능을 통해 여러 페이지에 걸친 회고 목록을 탐색할 수 있습니다.

---

## 🔗 주요 import 목록
| 항목                                           | 설명                   | 링크                                                     |
| -------------------------------------------- | -------------------- | ------------------------------------------------------ |
| `useEffect`, `useState`                      | 리액트 훅                | [React Docs](https://react.dev/reference/react)        |
| `fetchDiaryList`, `DiaryGroup`, `DiaryEntry` | 회고 데이터 요청 및 타입 정의    | [diaryApi.ts](../api/diaryApi.ts.md)                |
| `DiaryItem`                                  | 개별 회고 항목을 렌더링하는 컴포넌트 | [DiaryItem.tsx](../components/DiaryItem.tsx.md)     |
| `Pagination`                                 | 페이지 이동 컴포넌트          | [Pagination.tsx](../components/Pagination.tsx.md)   |
| `Header`                                     | 상단 네비게이션 헤더          | [Header.tsx](../../layout/components/Header.tsx.md) |


---

## 🧩 포함 컴포넌트 트리
``` text
DiaryListPage
├── Header
├── [반복] DiaryGroup
│   ├── 날짜 제목
│   ├── GPT 요약 (선택적)
│   └── [반복] DiaryItem
└── Pagination
```
---

## 📝 설명 및 주요 로직
useState 훅을 통해 페이지 번호(page), 회고 그룹(diaryGroups), 총 페이지 수(totalPages), 펼쳐진 회고 ID(openId) 상태를 관리합니다.

useEffect 훅에서 page 값이 변경될 때마다 fetchDiaryList를 호출하여 데이터를 로드합니다.

각 회고는 날짜별로 그룹화되어 출력되며, 각 날짜 아래에 DiaryItem이 나열됩니다.

GPT 요약은 해당 날짜에 존재할 경우 보여지며, diary.summary를 통해 출력됩니다.

Pagination 컴포넌트를 통해 사용자가 페이지를 이동할 수 있습니다.

---

## 📌 기타 참고
다크모드를 고려한 Tailwind CSS 클래스가 적용되어 있으며, 부드러운 색상 전환(transition-colors)도 설정되어 있습니다.

openId를 통해 한 번에 하나의 회고만 펼쳐지도록 제어하고 있습니다.

이 페이지는 /diary/list와 같이 사용자의 회고 목록을 보여주는 대표적인 라우트에 배치될 가능성이 높습니다.

