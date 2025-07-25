# 📄 calendarApi.ts
## 📁 위치
features/calendar/api/calendarApi.ts

---

## 🧭 역할
달력 화면에서 사용할 월간 회고 데이터를 API를 통해 가져오는 함수와 관련 타입들을 정의합니다.
사용자 감정, 회고 내용, GPT 요약 등을 포함하는 다이어리 데이터를 모델링합니다.

---

## 🔗 주요 export 목록
| 항목                      | 설명                     |
| ----------------------- | ---------------------- |
| `EmotionLevel`          | 감정 점수 (1\~5 범위)        |
| `DiaryEntry`            | 단일 회고 항목을 나타내는 타입      |
| `DailyDiaryData`        | 특정 날짜의 회고 목록과 GPT 요약   |
| `fetchMonthDiaryList()` | 월별 회고 데이터를 가져오는 API 함수 |


---

## 🧩 타입 및 함수 구조
```ts
type EmotionLevel = 1 | 2 | 3 | 4 | 5;
```
```ts
type DiaryEntry = {
  id: string;
  date: string;
  emotion: EmotionLevel;
  habitTags: string;
  feelingKo: string;
  feelingEn: string;
  content: string;
  feedback: string;
};
```
```ts
type DailyDiaryData = {
  date: string;
  entries: DiaryEntry[];
  summary?: string;
};
```

function fetchMonthDiaryList(selectedDate: string): Promise<DailyDiaryData[]>
📝 설명 및 주요 로직
EmotionLevel: 감정 점수는 1~5의 정수형 값으로 제한됩니다.

DiaryEntry:

하나의 회고 기록을 구성하는 모든 주요 정보를 포함합니다.

감정점수(emotion), 태그, 한글/영문 감정 표현, 일기 본문, GPT 피드백 포함

DailyDiaryData:

하나의 날짜에 속한 entries(회고 목록)와 해당 날짜의 summary(GPT 요약) 포함

fetchMonthDiaryList(selectedDate):

selectedDate는 'YYYY-MM-DD' 형식

이 날짜를 기반으로 월별 데이터를 요청함 (예: "2025-07-01" → 7월 전체 반환)

GET 요청 URL: /user/diaries/monthly?yearMonth=YYYY-MM-DD

---

## 📌 기타 참고
axiosInstance는 프로젝트 전역에서 인증 및 공통 설정이 적용된 Axios 인스턴스입니다.

이 API는 달력 화면의 Calendar.tsx와 useEffect 내에서 호출되며, 월간 회고 데이터를 기준으로 캘린더 셀을 구성합니다.

날짜 형식이 YYYY-MM-DD인 이유는 백엔드 파라미터가 yearMonth로 들어가더라도 일 단위 문자열을 요구하는 설계 때문일 수 있습니다.