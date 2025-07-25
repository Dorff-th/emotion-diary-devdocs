# 📄 statisticsApi.ts
## 📁 위치
features/statistics/api/statisticsApi.ts

---

## 🧭 역할
감정 통계 데이터를 백엔드로부터 받아오는 비동기 API 함수와 그 응답 타입을 정의하는 모듈입니다.
평균 감정 점수, 감정 빈도, 주간 추이, 요일별 평균 감정 등 다양한 통계 정보를 제공합니다.

---

## 🔗 주요 export 목록
| 항목                          | 설명                          |
| --------------------------- | --------------------------- |
| `EmotionStatisticsResponse` | 감정 통계 API 응답 타입 정의          |
| `fetchEmotionStatistics()`  | 감정 통계 데이터를 서버에서 가져오는 API 함수 |


---

## 🧩 타입 구조
```ts 
export interface EmotionStatisticsResponse {
  averageEmotion: number;
  emotionFrequency: Record<number, number>;
  weeklyTrend: {
    weekLabel: string;
    averageEmotion: number;
  }[];
  dayOfWeekAverage: Record<string, number>;
}
```
---

## 📝 설명 및 주요 로직
### 📌 fetchEmotionStatistics(startDate, endDate)
전달된 startDate, endDate를 파라미터로 /user/statistics/emotion 엔드포인트에 GET 요청을 보냄.

응답 데이터는 다음과 같은 네 가지 구조를 포함:

averageEmotion: 전체 평균 감정 점수 (1.0 ~ 5.0)

emotionFrequency: 감정 점수별 빈도수 (예: { 1: 3, 2: 5, ... })

weeklyTrend: 주차별 평균 감정 점수 추이 (예: 7/1~7/7 주차별 평균)

dayOfWeekAverage: 요일별 평균 감정 점수 (예: { MONDAY: 3.5, TUESDAY: 2.9, ... })

사용 위치: EmotionStatsPage.tsx
→ 여기서 호출되어 막대/선형/요일 차트와 요약 카드에 데이터 전달

### 📌 기타 참고
API 통신은 axiosInstance를 통해 이루어지며, 인증 토큰 등이 설정되어 있어야 함

date-fns와 함께 사용 시 startOfMonth, endOfMonth 등의 유틸과 조합하여 날짜 범위 지정 가능

