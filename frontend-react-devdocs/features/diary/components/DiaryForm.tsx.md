# 📄 DiaryForm.tsx
## 📁 위치
features/diary/components/DiaryForm.tsx

---

## 🧭 역할
사용자가 감정, 습관, 느낌 한마디, 회고 내용을 입력하고 GPT 피드백을 생성한 뒤 전체 회고를 저장할 수 있도록 돕는 폼 컴포넌트입니다.

---

## 🔗 주요 import 목록
| 항목                   | 설명                       | 링크                                                                   |
| -------------------- | ------------------------ | -------------------------------------------------------------------- |
| `EmotionSelector`    | 감정 점수 선택 UI              | [EmotionSelector.tsx](./EmotionSelector.tsx.md)                      |
| `HabitChecklist`     | 체크리스트 형태의 습관 선택 UI       | [HabitChecklist.tsx](./HabitChecklist.tsx.md)                        |
| `FeelingInput`       | 오늘의 느낌 한마디 (한글) 입력       | [FeelingInput.tsx](./FeelingInput.tsx.md)                            |
| `DiaryTextarea`      | 회고 일기 텍스트 입력란            | [DiaryTextarea.tsx](./DiaryTextarea.tsx.md)                          |
| `FeedbackTypeSelect` | GPT 피드백 스타일 선택           | [FeedbackTypeSelect.tsx](./FeedbackTypeSelect.tsx.md)                |
| `SubmitButton`       | 회고 저장 버튼 (로딩 상태 포함)      | [SubmitButton.tsx](./SubmitButton.tsx.md)                            |
| `GPTFeedbackModal`   | GPT 피드백 생성 중/완료 시 모달창    | [GPTFeedbackModal.tsx](../../gpt/components/GPTFeedbackModal.tsx.md) |
| `FeedbackType`       | GPT 피드백 스타일 타입 정의        | [feedbackTypes.ts](../../gpt/types/feedbackTypes.ts.md)              |
| `axiosInstance`      | API 요청을 위한 axios 설정 인스턴스 | [axiosInstance.ts](../../../lib/axios/axiosInstance.ts.md)           |


---

## 🧩 포함 컴포넌트 트리
```text
DiaryForm
├── EmotionSelector
├── HabitChecklist
├── FeelingInput
├── DiaryTextarea
├── FeedbackTypeSelect
├── SubmitButton
└── GPTFeedbackModal
```
---

## 📝 설명 및 주요 로직
상태 관리:

emotion: 감정 점수 (1~5 등)

habits: 체크한 습관 리스트

feelingText: 오늘의 기분 한마디 (한글)

feelingEnglish: 오늘의 기분 한마디 (영문, 추후 기능용)

diary: 오늘의 회고 일기

feedbackType: GPT 피드백 스타일 선택 (e.g., random, kind, scold)

gptMessage: GPT 응답 메시지 (모달에 표시됨)

showModal, isSaving, isSaveSuccess: 저장 및 피드백 상태 관리

주요 로직 흐름:

GPT 피드백 생성:

/user/gpt/diary-feedback API 호출로 content + feedbackType 전송 → 응답 받은 피드백 표시

회고 저장:

/user/diary API로 emotion, habits, feelingText, feelingEnglish, diary, gptFeedback 등 전송

저장 성공 여부에 따라 모달 메시지 및 저장 성공 상태 업데이트

사용자 입력 유효성 검사:

감정 점수와 회고 일기가 비어있을 경우 저장 불가 (경고 알림)

---

## 📌 기타 참고
모달이 먼저 뜨고 GPT 응답이 오면 내용이 교체되므로 UX 흐름이 매끄럽습니다.

전체 저장 로직은 GPT 호출 후 이어서 실행되는 구조이며, 이 덕분에 사용자에게는 자연스러운 흐름으로 피드백과 저장을 제공합니다.

GPT 실패 시 fallback 메시지 제공 (예: "오늘도 수고했어요...").