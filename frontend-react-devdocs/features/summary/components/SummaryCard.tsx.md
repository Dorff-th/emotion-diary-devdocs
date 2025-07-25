# 📄 SummaryCard.tsx
## 📁 위치
features/summary/components/SummaryCard.tsx

---

# 🧭 역할
오늘 회고에 대한 GPT 요약 결과를 보여주는 카드 컴포넌트입니다.
GPT 요약이 존재하는 경우 출력하고, 없을 경우 대체 안내 문구를 표시합니다.
추후에는 요약 재생성 기능도 포함될 수 있도록 주석 처리된 버튼이 존재합니다.

---

## 🔗 주요 import 목록
| 항목                     | 설명                   | 링크                                                       |
| ---------------------- | -------------------- | -------------------------------------------------------- |
| `useToastHelper`       | 토스트 메시지 출력을 위한 커스텀 훅 | [toastHelper.ts](../../../features/toast/utils/toastHelper.ts.md) |
| `fetchTodayGptSummary` | 오늘 GPT 요약 API 호출 함수  | [summaryApi.ts](../api/summaryApi.ts.md)                 |


---

## 🧩 포함 컴포넌트 트리
text
복사
편집
SummaryCard
├── GPT 요약 결과 텍스트
└── (요약이 없을 경우) 안내 문구
    └── (주석 처리된) "요약 생성" 버튼

## 📝 설명 및 주요 로직
Props는 두 가지를 받음:

summary?: 외부에서 전달된 요약 문자열 (현재 미사용)

onSummaryUpdated: 추후 요약 생성 시 외부 상태 업데이트 콜백

내부 상태:

gptSummary: API에서 불러온 요약 내용 저장용

loading: 요약 로딩 여부

toast: showSuccess, showError 메시지 출력 용도

tsx
복사
편집
useEffect(() => {
  fetchTodayGptSummary()
    .then(data => setGptSummary(data.summary))
    .finally(() => setLoading(false));
}, []);
GPT 요약이 존재하면 렌더링하고, 없으면 "아직 요약이 없어요!" 문구 출력

버튼(요약 생성하기)은 주석 처리되어 있지만 향후 사용될 수 있도록 로직이 준비되어 있음

---

## 📌 기타 참고
실제 요약 내용은 fetchTodayGptSummary()를 통해 별도 API 호출로 불러오며, useSummaryData()를 사용하지 않음

추후 handleGenerateSummary() 같은 생성 트리거를 활성화하면 사용자가 수동으로 요약을 생성할 수 있게 됨

Tailwind CSS를 활용하여 부드럽고 일관된 카드 스타일 구성 (bg-purple-50, shadow-sm, rounded-xl 등)

