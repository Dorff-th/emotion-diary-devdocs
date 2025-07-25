#📄 EmotionSelector.tsx
##📁 위치
features/diary/components/EmotionSelector.tsx

---

## 🧭 역할
사용자가 오늘의 감정 상태를 이모지 버튼을 통해 선택할 수 있도록 제공하는 감정 선택 UI 컴포넌트입니다.

---

## 🔗 주요 import 목록
| 항목            | 설명                     | 링크                                         |
| ------------- | ---------------------- | ------------------------------------------ |
| `clsx`        | 조건부 스타일링을 위한 유틸 함수     | 외부 라이브러리                                   |
| `emotionList` | 감정 이모지와 값, 라벨을 정의한 리스트 | [emotionMap.ts](../types/emotionMap.ts.md) |


---

##🧩 포함 컴포넌트 트리
```text
EmotionSelector
└── 감정 이모지 버튼들 (emotionList.map으로 반복)
```
---
## 📝 설명 및 주요 로직
props:

selected: 현재 선택된 감정 값 (숫자형, 예: 1~5)

onChange: 감정 선택 시 호출되는 콜백 함수

주요 동작:

emotionList 배열을 순회하며 이모지 버튼 렌더링

버튼 클릭 시 해당 감정 값(item.value)을 상위로 전달 (onChange)

현재 선택된 감정은 scale, border 등 시각적 강조 적용

스타일:

Tailwind 기반 스타일링 (다크모드 대응)

선택된 버튼은 scale-125, border-blue-400, rounded-full 강조

미선택된 버튼은 opacity-70 처리로 대비 효과 부여

---

## 📌 기타 참고
UX 향상을 위해 버튼에 title={item.label} 속성이 있어 툴팁 제공

emotionList는 확장 가능한 구조로, 추후 감정 추가/변경이 쉬움

외부 상태를 관리하지 않고 부모로부터 상태를 props로 받는 구조이므로 재사용성이 높음

