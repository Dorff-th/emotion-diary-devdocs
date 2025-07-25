# 📄 FeedbackCard.tsx
## 📁 위치
features/summary/components/FeedbackCard.tsx

---

# 🧭 역할
GPT가 생성한 회고 피드백을 보여주는 카드 컴포넌트입니다.
피드백이 존재하면 렌더링하고, 없을 경우 대체 문구를 보여줍니다.
사용자는 이 컴포넌트에서 피드백을 직접 생성할 수는 없습니다.
(요약 화면에서는 오직 조회만 가능하도록 설계됨)

---

# 🔗 주요 import 목록
| 항목                  | 설명                          | 링크                                                       |
| ------------------- | --------------------------- | -------------------------------------------------------- |
| `useToastHelper`    | 토스트 알림 유틸리티 훅 (현재는 사용하지 않음) | [toastHelper.ts](../../../features/toast/utils/toastHelper.ts.md) |
| `createGptFeedback` | GPT 피드백 생성 API (현재는 주석 처리)  | [summaryApi.ts](../api/summaryApi.ts.md) *(주석 상태)*       |


---

# 🧩 포함 컴포넌트 트리
text
복사
편집
FeedbackCard
├── GPT 피드백 텍스트
└── (피드백이 없을 경우) 안내 문구
    └── (주석 처리된) "피드백 생성" 버튼

---

# 📝 설명 및 주요 로직
Props:

feedback?: 전달된 GPT 피드백 문자열

onFeedbackUpdated: 피드백 생성 시 외부 상태 업데이트 함수 (현재는 사용되지 않음)

내부 상태:

loading: 버튼 클릭 시 로딩 여부 (현재 버튼은 비활성화 상태)

useToastHelper()는 현재 UI에서 사용되지 않으나 구조상 선언은 남겨둠

피드백이 있을 경우:

tsx
복사
편집
<p className="text-sm text-gray-700 whitespace-pre-wrap">{feedback}</p>
피드백이 없을 경우:

tsx
복사
편집
<p className="text-sm text-gray-500 mb-2">아직 GPT 피드백이 없어요.</p>
handleGenerateFeedback 함수는 완전히 주석 처리되어 있음.
추후 피드백 수동 생성 기능을 위해 준비된 코드.

# 📌 기타 참고
이 컴포넌트는 SummaryPage.tsx 내 FeedbackCard 영역에서 사용됨

"GPT 요약은 가능하지만, 피드백은 단지 조회만 허용"하는 UX 정책에 따라 버튼은 숨겨져 있음

useToastHelper()는 추후 버튼이 다시 활성화될 경우 사용 가능성을 염두에 두고 남겨둠

