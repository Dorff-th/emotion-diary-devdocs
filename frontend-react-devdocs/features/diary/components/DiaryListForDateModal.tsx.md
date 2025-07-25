# 📄 DiaryListForDateModal.tsx
## 📁 위치
features/diary/components/DiaryListForDateModal.tsx

---

## 🧭 역할
특정 날짜를 클릭했을 때, 해당 날짜의 회고 목록을 모달로 보여주는 컴포넌트입니다.
개별 회고 펼침, GPT 요약 생성, 감정 이모지 표시 등 다양한 인터랙션을 포함합니다.

---

## 🔗 주요 import 목록
| 항목                                | 설명                         | 링크                                                     |
| --------------------------------- | -------------------------- | ------------------------------------------------------ |
| `emotionEmojiMap`, `EmotionLevel` | 감정 점수에 따라 이모지를 반환하는 매핑 객체  | [emotionMap.ts](../../diary/types/emotionMap.ts.md)    |
| `DiaryEntry`                      | 회고 데이터 타입 정의               | [calendarApi.ts](../../calendar/api/calendarApi.ts.md) |
| `generateGptSummary`              | 특정 날짜 회고를 GPT로 요약하는 API 함수 | [gptSummaryApi.ts](../../gpt/api/gptSummaryApi.ts.md)  |
| `useToastHelper`                  | 토스트 메시지 헬퍼 (성공/에러 알림)      | [toastHelper.ts](../../toast/utils/toastHelper.ts.md)  |
| `X`                               | 닫기 아이콘 (Lucide 아이콘 라이브러리)  | [Lucide Icon Docs](https://lucide.dev/icons/x)         |


---

## 🧩 포함 컴포넌트 구조
```text
DiaryListForDateModal
├── Header (날짜 + 닫기버튼)
├── Summary 영역 (GPT 요약 or 버튼)
├── 회고 목록 sortedList.map(...)
│   └── 감정 이모지, 한글/영문 감정 표현, 일기 본문 등 표시
└── GPT 요약 버튼 (generateGptSummary API 호출)
```

## 📝 설명 및 주요 로직
props:

date: 현재 선택된 날짜 (형식: YYYY-MM-DD)

diaryEntries: 해당 날짜의 회고 데이터

summary: 기존 GPT 요약 문자열

onSummaryGenerated: 요약 완료 후 상위에 알림을 줄 수 있는 콜백

로컬 상태:

openEntryId: 펼쳐진 회고 ID

gptSummary: 현재 표시 중인 요약 내용

loading: GPT 요약 요청 중 여부

기능:

회고 목록은 최신순으로 정렬 (id 기준 내림차순)

GPT 요약이 없을 경우 버튼 표시 → 클릭 시 generateGptSummary 호출

요약 성공 시 모달 내 요약 표시 + 토스트 성공 알림

에러 발생 시 토스트로 실패 메시지 표시

---

## 📌 기타 참고
UI는 다크모드에 대응하며, 감정 이모지와 감정 문구(한/영)도 함께 시각화됩니다.

gptSummary는 Calendar.tsx와 연결되어 있어 달력 전체 상태와도 연동됩니다.

닫기 버튼은 Lucide 아이콘(X)으로 구성되어 있으며, 상위 컴포넌트와 onClose()로 연결됩니다.

