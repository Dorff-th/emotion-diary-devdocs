# 📄 FeedbackTypeSelect.tsx
## 📁 위치
features/diary/components/FeedbackTypeSelect.tsx

---

## 🧭 역할
사용자가 원하는 GPT 피드백 스타일(예: 위로, 칭찬, 갈굼 등)을 선택할 수 있는 &lt;select&gt; 드롭다운 컴포넌트입니다.

---

## 🔗 주요 import 목록
| 항목                 | 설명                       | 링크                                                      |
| ------------------ | ------------------------ | ------------------------------------------------------- |
| `FeedbackType`     | 피드백 스타일을 문자열 리터럴로 정의한 타입 | [feedbackTypes.ts](../../gpt/types/feedbackTypes.ts.md) |
| `feedbackStyleMap` | 스타일별 라벨, 이모지 정보를 담은 맵 객체 | [feedbackTypes.ts](../../gpt/types/feedbackTypes.ts.md) |


---

## 🧩 포함 컴포넌트 트리
``` text
FeedbackTypeSelect
└── select
    └── option[] (feedbackStyleMap 기반)
```

---

## 📝 설명 및 주요 로직
props:

value: 현재 선택된 피드백 타입 (FeedbackType 타입)

onChange: 피드백 타입 변경 시 상위로 전달하는 콜백 함수

주요 동작:

feedbackStyleMap의 key-value 쌍을 Object.entries()로 순회하며 <option> 요소를 생성

사용자가 옵션을 변경하면 onChange를 통해 부모 컴포넌트에 새로운 타입을 전달

옵션 구성:

각 옵션은 이모지 + 설명 텍스트 ({style.emoji} {style.label})로 구성되어 직관적임

예시: 😢 위로, 🎉 칭찬, 🤬 갈굼 등

스타일:

Tailwind 기반 다크모드/라이트모드 대응

select 요소는 전체 너비 사용, 시각적 일관성 유지

---

### 📌 기타 참고
feedbackStyleMap은 사용자가 직관적으로 피드백 타입을 이해할 수 있도록 도와주는 UX 개선 요소

추후 새로운 스타일을 추가하거나 제거하려면 feedbackTypes.ts만 수정하면 자동 반영됨

드롭다운 UI는 간결하면서도 감정적 피드백을 명확하게 표현해 사용자의 선택을 돕습니다