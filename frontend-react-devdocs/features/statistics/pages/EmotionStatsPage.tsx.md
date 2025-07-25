# 📄 EmotionStatsPage.tsx
## 📁 위치
features/statistics/pages/EmotionStatsPage.tsx

---

## 🧭 역할
사용자의 감정 데이터를 기간별로 분석하여 시각화된 통계를 보여주는 페이지입니다.
막대/선형 차트 및 요약 카드 등을 통해 감정 추이를 한눈에 파악할 수 있도록 구성되어 있습니다.

---

## 🔗 주요 import 목록
| 항목                                     | 설명                         | 링크                                                             |
| -------------------------------------- | -------------------------- | -------------------------------------------------------------- |
| `DatePicker`                           | 날짜 선택 UI 라이브러리             | [react-datepicker](https://reactdatepicker.com/)               |
| `fetchEmotionStatistics`               | 감정 통계 데이터를 불러오는 API 함수     | [statisticsApi.ts](../api/statisticsApi.ts)                    |
| `format`, `startOfMonth`, `endOfMonth` | 날짜 포맷 및 계산을 위한 유틸 함수       | [date-fns](https://date-fns.org/)                              |
| `EmotionBarChart`                      | 전체 감정 분포를 나타내는 막대 차트 컴포넌트  | [EmotionBarChart.tsx](../components/EmotionBarChart.tsx)       |
| `WeeklyLineChart`                      | 주간 감정 추이를 나타내는 선형 차트 컴포넌트  | [WeeklyLineChart.tsx](../components/WeeklyLineChart.tsx)       |
| `DayOfWeekBarChart`                    | 요일별 감정 빈도를 나타내는 막대 차트 컴포넌트 | [DayOfWeekBarChart.tsx](../components/DayOfWeekBarChart.tsx)   |
| `getDateRange`                         | 선택된 기간에 따른 시작/끝 날짜를 계산     | [dateUtils.ts](../../../utils/dateUtils.ts)                    |
| `PeriodOption`                         | 기간 선택 옵션 타입 정의             | [statisticsTypes.ts](../types/statisticsTypes.ts)              |
| `Header`                               | 상단 페이지 제목 및 레이아웃           | [Header.tsx](../../layout/components/Header.tsx)            |
| `EmotionSummaryCard`                   | 감정 통계 요약 카드                | [EmotionSummaryCard.tsx](../components/EmotionSummaryCard.tsx) |


---

## 🧩 포함 컴포넌트 트리
```text
편집
EmotionStatsPage
├── Header
├── DatePicker (기간 선택)
├── EmotionSummaryCard
├── EmotionBarChart
├── WeeklyLineChart
└── DayOfWeekBarChart
```
---

## 📝 설명 및 주요 로직
period 상태를 통해 사용자가 선택한 기간을 관리 (this-month, last-month 등).

getDateRange()로 기간에 따른 startDateStr, endDateStr를 계산.

fetchEmotionStatistics(start, end) API를 통해 감정 통계를 받아옴.

통계 데이터는 emotionSummary, weeklyAverages, dayOfWeekCounts로 분리되어 각 차트 및 카드에 전달됨.

시각화는 EmotionBarChart, WeeklyLineChart, DayOfWeekBarChart로 구성됨.

DatePicker로 날짜를 직접 선택할 수도 있고, 상단 select 박스로 기간도 선택 가능.

---

## 📌 기타 참고
초기 진입 시 기본 기간은 '이번 달(this-month)'로 설정됩니다.

데이터가 없을 경우 적절한 fallback UI는 아직 구현되지 않았을 수 있습니다.

모든 감정 통계는 서버에서 가공되어 내려오는 구조로, 클라이언트에서 추가 가공은 최소화됨.

