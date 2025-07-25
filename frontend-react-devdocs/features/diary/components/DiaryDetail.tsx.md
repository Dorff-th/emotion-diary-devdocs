# 📄 DiaryDetail.tsx
## 📁 위치
features/diary/components/DiaryDetail.tsx

---

# 🧭 역할
DiaryItem 컴포넌트의 상세 내용 영역입니다. 사용자가 회고 항목을 클릭하여 확장했을 때 보여지는 상세 정보(내용, 감정, 영어 표현, 습관 태그 등)를 렌더링합니다.

---

## 🔗 주요 import 목록
항목	설명	링크
| 항목                                                   | 설명                  | 링크                                         |
| ---------------------------------------------------- | ------------------- | ------------------------------------------ |
| `DiaryEntry`                                         | 개별 회고 항목의 타입        | [diaryApi.ts](../api/diaryApi.ts.md)       |
| `emotionEmojiMap`, `emotionLabelMap`, `EmotionLevel` | 감정 레벨을 이모지 및 라벨로 매핑 | [emotionMap.ts](../types/emotionMap.ts.md) |


---

## 🧩 포함 컴포넌트 트리
```text
DiaryDetail
└── <div> (텍스트 위주 출력)
    ├── 감정 이모지 및 텍스트
    ├── 한글/영문 감정 표현
    ├── 습관 태그
    ├── 회고 본문
    └── GPT 피드백
📝 설명 및 주요 로직
```
DiaryEntry 타입의 diary 객체를 props로 받아 사용합니다.

감정 점수(emotion)를 emotionEmojiMap과 emotionLabelMap을 통해 시각적으로 보여줍니다.

한글 감정(feelingKo)과 영어 감정(feelingEn)을 함께 출력하여 감정 표현 학습의 용도로 활용 가능합니다.

습관 태그(habitTags)는 문자열 형태로, 쉼표 또는 공백으로 구분된 키워드를 태그 형태로 나열합니다.

회고 본문(content)과 GPT 피드백(feedback)을 별도 영역에 나눠서 보여줍니다.

---

## 📌 기타 참고
부모 컴포넌트 DiaryItem의 상태(isOpen)에 따라 렌더링 여부가 결정되며, 펼쳐질 때에만 이 컴포넌트가 출력됩니다.

CSS 클래스 또는 Tailwind 스타일로 구조를 꾸며 사용자의 감정 회고가 한눈에 들어오도록 구성됩니다.

다크 모드를 고려한 디자인일 가능성이 높습니다 (상위에서 적용됨).

