# 📄 WeeklyLineChart.tsx
## 📁 위치
features/statistics/components/WeeklyLineChart.tsx

---

## 🧭 역할
주간 단위로 집계된 감정 평균치를 선형 차트(LineChart)로 시각화하여, 감정의 흐름이나 패턴을 파악할 수 있도록 도와주는 컴포넌트입니다.

---

## 🔗 주요 import 목록
| 항목                                                                | 설명                           | 링크                                           |
| ----------------------------------------------------------------- | ---------------------------- | -------------------------------------------- |
| `LineChart`, `Line`, `XAxis`, `YAxis`, `Tooltip`, `CartesianGrid` | 선형 차트 구성 요소 (Recharts 라이브러리) | [recharts 공식문서](https://recharts.org/en-US/) |
| `React`                                                           | React 기본 import              | -                                            |


---

## 🧩 포함 컴포넌트 트리
```text
WeeklyLineChart
└── LineChart
    ├── CartesianGrid
    ├── XAxis (weekLabel)
    ├── YAxis (1 ~ 5 범위)
    ├── Tooltip
    └── Line (averageEmotion)
```

---


## 📝 설명 및 주요 로직
trend prop은 { weekLabel, averageEmotion } 객체 배열로, weekLabel은 주차(예: "7/1~7/7")를 의미.

LineChart의 데이터로 trend 배열이 주입됩니다.

X축: weekLabel (문자열), Y축: 감정 점수(1~5 사이).

YAxis는 domain={[1, 5]}로 고정되어 감정 점수 범위가 명확하게 시각화됩니다.

Line은 monotone 타입이며, 감정 흐름의 부드러운 곡선을 생성.

stroke="#8884d8"로 기본 보라색 계열 선 스타일 적용.

---

## 📌 기타 참고
감정 점수가 평균값으로 계산되므로 부드러운 추이 시각화에 적합.

상위 컴포넌트인 EmotionStatsPage.tsx에서 사용되며, 기간 선택에 따라 동적으로 변경되는 데이터 기반.

width와 height가 고정값이므로, 반응형 처리가 필요한 경우 별도 설정 필요.