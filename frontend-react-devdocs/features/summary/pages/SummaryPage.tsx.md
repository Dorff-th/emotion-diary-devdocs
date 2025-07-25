# 📄 SummaryPage.tsx
## 📁 위치
features/summary/pages/SummaryPage.tsx

---

## 🧭 역할
사용자가 오늘 작성한 회고 데이터를 기반으로 감정, 습관, GPT 요약, 피드백 등을 보여주는 오늘 회고 요약 페이지입니다.
사용자 맞춤 정보와 AI 요약 결과를 한 화면에 시각적으로 제공하며, 회고 입력 후 진입하는 첫 화면으로 사용됩니다.

---

## 🔗 주요 import 목록
항목	설명	링크
| 항목                 | 설명                          | 링크                                                            |
| ------------------ | --------------------------- | ------------------------------------------------------------- |
| `useSummaryData`   | 오늘 회고 요약 데이터를 불러오는 커스텀 훅    | [useSummaryData.ts](../hooks/useSummaryData.ts.md)            |
| `EmotionLevel`     | 감정 상태 enum 타입               | [emotionMap.ts](../../../features/diary/types/emotionMap.ts.md)        |
| `TodayEmotionCard` | 감정 점수, 한글/영문 감정 표현 카드 컴포넌트  | [TodayEmotionCard.tsx](../components/TodayEmotionCard.tsx.md) |
| `TodayHabitCard`   | 체크된 오늘의 습관들을 보여주는 컴포넌트      | [TodayHabitCard.tsx](../components/TodayHabitCard.tsx.md)     |
| `SummaryCard`      | GPT로 생성된 요약 내용 표시 및 수정 컴포넌트 | [SummaryCard.tsx](../components/SummaryCard.tsx.md)           |
| `FeedbackCard`     | GPT로 생성된 피드백 표시 및 수정 컴포넌트   | [FeedbackCard.tsx](../components/FeedbackCard.tsx.md)         |

---


## 🧩 포함 컴포넌트 트리

SummaryPage
├── TodayEmotionCard
├── TodayHabitCard
├── SummaryCard
└── FeedbackCard

---

## 📝 설명 및 주요 로직
useSummaryData() 커스텀 훅을 통해 오늘 날짜에 해당하는 회고 데이터(summary)와 로딩 상태를 가져옴

GPT 요약과 피드백은 내부 상태(gptSummary, gptFeedback)로 별도 관리하며, summary 값이 바뀌면 초기화됨

summary.habitTags는 JSON 문자열 형태로 저장되어 있어 JSON.parse()로 파싱

로딩 중일 경우 "불러오는 중...", 데이터가 없을 경우 "오늘 회고가 없습니다!" 메시지를 보여줌

4가지 카드 컴포넌트를 렌더링:

감정 카드 (TodayEmotionCard)

습관 카드 (TodayHabitCard)

요약 카드 (SummaryCard)

피드백 카드 (FeedbackCard)

각 카드의 UI는 Tailwind CSS를 활용한 정렬 및 스타일링 적용

## 📌 기타 참고
각 카드 컴포넌트는 props로 데이터를 받고, 일부는 내부 상태 업데이트용 콜백(onSummaryUpdated, onFeedbackUpdated)을 제공합니다.

emotion, feelingKo, feelingEn, habitTags, summary, feedback은 DiaryEntry API의 응답에서 사용되는 주요 필드입니다.

이 화면은 UserHomePage.tsx에서 포함되며 로그인 후 진입하는 첫 메인 화면입니다.