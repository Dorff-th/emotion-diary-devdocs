# 📄 EmotionSummaryCard.tsx
## 📁 위치
features/statistics/components/EmotionSummaryCard.tsx

---

## 🧭 역할
평균 감정 점수를 기반으로 이모지와 메시지를 시각적으로 표현하는 요약 카드 컴포넌트입니다.
사용자에게 직관적인 피드백을 제공하여 감정 상태를 감성적으로 전달합니다.

---

## 🔗 주요 import 목록
| 항목      | 설명              | 링크 |
| ------- | --------------- | -- |
| `React` | React 기본 import | -  |


---

## 🧩 포함 컴포넌트 트리
```text
EmotionSummaryCard
└── getEmotionVisual(score)
    ├── emoji: 감정 점수에 따른 이모지
    └── message: 감정 상태에 대한 텍스트 메시지
```

## 📝 설명 및 주요 로직
average prop은 평균 감정 점수 (1.0 ~ 5.0).

내부 유틸 함수 getEmotionVisual(score)은 점수에 따라 다음 이모지 및 메시지를 리턴:

≥ 4.5: 🤩 최고의 기분이에요!

≥ 4.0: 😄 기분 좋은 날들이 많았어요!

≥ 3.0: 🙂 평범한 하루들이었어요.

≥ 2.0: 😐 조금 지쳤을지도 몰라요.

< 2.0: 😢 기운 내요. 내일은 더 나을 거예요!

시각적으로는 배경색과 그림자 스타일을 통해 카드 형태로 렌더링 (Tailwind CSS 활용).

---

## 📌 기타 참고
감정 점수의 소수점 두 자리까지 표현 (toFixed(2)).

사용자에게 긍정적이고 따뜻한 피드백을 주는 감정 기반 UX 요소로 설계됨.

