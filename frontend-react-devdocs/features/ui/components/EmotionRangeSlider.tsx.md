# 📄 EmotionRangeSlider.tsx
## 📁 위치
features/ui/components/EmotionRangeSlider.tsx

---

## 🧭 역할
감정 점수를 1점부터 5점까지 선택할 수 있는 커스텀 범위 슬라이더입니다.
감정 검색이나 통계 필터링 시 사용자의 감정 점수 범위를 시각적으로 설정할 수 있도록 도와줍니다.

---

## 🔗 주요 import 목록
| 항목       | 설명                   | 링크                                                           |
| -------- | -------------------- | ------------------------------------------------------------ |
| `Slider` | MUI에서 제공하는 슬라이더 컴포넌트 | [MUI Slider Docs](https://mui.com/material-ui/react-slider/) |
| `React`  | React 기본 import      | -                                                            |


---

## 🧩 포함 컴포넌트 트리
```text
EmotionRangeSlider
└── Slider (MUI)
    ├── valueLabelDisplay: "auto"
    ├── min: 1
    ├── max: 5
    ├── marks: emotionMarks (이모지 라벨)
    └── step: 1
```

## 📝 설명 및 주요 로직
value: 현재 슬라이더 값, [number, number] 형태로 범위 지정됨

onChange: 값 변경 시 호출되는 콜백, 상위 컴포넌트에서 상태 반영

emotionMarks: 각 감정 점수에 이모지 라벨을 매핑하여 시각적으로 이해를 돕는 마크

1: 😞, 2: 😐, 3: 🙂, 4: 😊, 5: 😄

Slider 구성:

valueLabelDisplay="auto": 현재 값이 슬라이더 위에 표시됨

step={1}: 1단위로 이동

min={1}, max={5}: 감정 점수 범위

marks={emotionMarks}: 점수별 감정 이모지 마킹

---

## 📌 기타 참고
감정 점수는 1~5의 정수 값이며, 중간값 없이 정확한 점수만 선택 가능

범위 형태(value: [min, max])로 구성되어 있어 감정 필터링에 적합

주요 사용 위치: SearchResultPage.tsx 검색 조건 UI