# 📄 DayOfWeekBarChart.tsx
## 📁 위치
features/statistics/components/DayOfWeekBarChart.tsx

---

## 🧭 역할
요일별 평균 감정 점수를 막대 차트로 시각화하여, 특정 요일에 감정 기복이 있었는지 한눈에 확인할 수 있도록 해주는 컴포넌트입니다.

---

## 🔗 주요 import 목록
항목	설명	링크
| 항목                                                                | 설명                           | 링크                                           |
| ----------------------------------------------------------------- | ---------------------------- | -------------------------------------------- |
| `LineChart`, `Line`, `XAxis`, `YAxis`, `Tooltip`, `CartesianGrid` | 선형 차트 구성 요소 (Recharts 라이브러리) | [recharts 공식문서](https://recharts.org/en-US/) |
| `React`                                                           | React 기본 import              | -                                            |


---

## 🧩 포함 컴포넌트 트리
```text
DayOfWeekBarChart
└── BarChart
    ├── XAxis (day)
    ├── YAxis (1~5 범위)
    ├── Tooltip
    └── Bar (average)
```

## 📝 설명 및 주요 로직
dayAverage는 요일(MONDAY, TUESDAY, ...)을 키로, 평균 감정 점수를 값으로 가지는 객체입니다.

---

dayOrder 배열을 기준으로 데이터를 정렬하여 요일 순서 유지 (map()으로 누락된 요일은 0으로 처리).

X축: 요일 (day), Y축: 감정 점수 (1~5).

Tooltip 포함으로 바에 마우스 오버 시 상세 수치 표시.

막대 색상은 #82ca9d (연녹색 계열)로 시각적 구분 제공.

## 📌 기타 참고
요일별 데이터가 누락될 경우 기본값 0으로 보정 처리.

감정 점수 범위는 고정(domain={[1, 5]})으로 안정적인 스케일 유지.

상위 컴포넌트인 EmotionStatsPage.tsx에서 함께 사용됩니다.