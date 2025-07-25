# 📄 DiaryItem.tsx
## 📁 위치
features/diary/components/DiaryItem.tsx

---

# 🧭 역할
개별 회고 항목을 리스트 형태로 보여주는 컴포넌트입니다. 사용자가 클릭하여 상세 내용을 펼치거나 닫을 수 있으며, 애니메이션 효과가 적용되어 UX를 부드럽게 만듭니다.

---

## 🔗 주요 import 목록
| 항목                                                   | 설명                  | 링크                                                    |
| ---------------------------------------------------- | ------------------- | ----------------------------------------------------- |
| `motion`, `AnimatePresence`                          | 애니메이션 효과 제공 라이브러리   | [framer-motion 공식 문서](https://www.framer.com/motion/) |
| `DiaryEntry`                                         | 회고 항목 데이터 타입        | [diaryApi.ts](../api/diaryApi.ts.md)                  |
| `DiaryDetail`                                        | 회고 상세 내용을 보여주는 컴포넌트 | [DiaryDetail.tsx](./DiaryDetail.tsx.md)               |
| `emotionEmojiMap`, `emotionLabelMap`, `EmotionLevel` | 감정 수준 관련 상수 및 타입    | [emotionMap.ts](../types/emotionMap.ts.md)            |


---

## 🧩 포함 컴포넌트 트리
```text
DiaryItem
├── motion.div (요약 정보, 클릭 시 확장)
└── AnimatePresence
    └── motion.div (DiaryDetail)
```
---    
## 📝 설명 및 주요 로직
DiaryItemProps를 통해 아래와 같은 props를 전달받습니다:

diary: DiaryEntry 타입의 회고 데이터

isOpen: 상세 내용이 펼쳐져 있는지 여부

onToggle: 열림/닫힘 상태를 전환하는 핸들러

motion.div와 AnimatePresence를 이용해 회고 요약 → 상세 전환 시 자연스러운 애니메이션 효과가 제공됩니다.

회고의 감정 상태는 emotionEmojiMap 및 emotionLabelMap을 통해 이모지 및 텍스트로 시각화됩니다.

---

## 📌 기타 참고
이 컴포넌트는 DiaryListPage.tsx에서 여러 개의 DiaryItem을 날짜별로 나열할 때 사용됩니다.

DiaryDetail은 해당 회고의 상세 정보 (내용, GPT 피드백 등)를 출력하며, 펼쳐진 상태일 때만 렌더링됩니다.

감정 점수는 emotion 숫자에 따라 적절한 이모지/라벨로 변환되어 출력됩니다.

