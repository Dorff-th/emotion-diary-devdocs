# 📄 FeelingInput.tsx
## 📁 위치
features/diary/components/FeelingInput.tsx

---

## 🧭 역할
오늘 기분을 한글로 입력받고, 해당 기분을 기반으로 GPT에게 영어 표현을 추천받는 기능을 제공하는 입력 필드 컴포넌트입니다.

---

## 🔗 주요 import 목록
| 항목                       | 설명                           | 링크                                                                              |
| ------------------------ | ---------------------------- | ------------------------------------------------------------------------------- |
| `axiosInstance`          | GPT API 호출을 위한 Axios 설정 인스턴스 | [axiosInstance.ts](../../../lib/axios/axiosInstance.ts.md)                      |
| `useToastHelper`         | 에러 메시지를 토스트로 표시하는 유틸리티 훅     | [toastHelper.ts](../../toast/utils/toastHelper.ts.md)                           |
| `GptFeelingLoadingModal` | GPT 응답 대기 중 표시되는 로딩 모달 컴포넌트  | [GptFeelingLoadingModal.tsx](../../ui/components/GptFeelingLoadingModal.tsx.md) |
| `clsx`                   | 조건부 스타일 클래스 결합을 위한 유틸리티      | 외부 라이브러리                                                                        |


---

## 🧩 포함 컴포넌트 트리
```text
FeelingInput
├── GptFeelingLoadingModal
└── div.wrapper
    ├── input[type="text"]
    ├── button[GPT 추천]
    └── button[] (GPT 추천 결과 리스트)
```    
## 📝 설명 및 주요 로직
props:

value: 한글 기분 문장 (input value)

onChange: 한글 입력 변경 시 호출되는 콜백

selectedEnglish: 선택된 영어 표현 문자열

onEnglishSelect: 영어 표현 선택 시 호출되는 콜백

주요 기능 흐름:

사용자가 한글 기분 문장을 입력

"GPT 추천" 버튼 클릭 → /user/gpt/feeling API 호출

응답으로 영어 표현 리스트를 받아서 버튼 목록으로 렌더링

사용자가 표현 선택 → onEnglishSelect로 상위에 전달

사용자 경험:

GPT 요청 중 GptFeelingLoadingModal을 통해 피드백 제공

추천 결과는 클릭 가능한 버튼으로 제시 → 직관적 선택 가능

ToastHelper를 통해 실패 시 오류 메시지 제공

스타일:

Tailwind 기반의 다크모드/라이트모드 스타일링

선택된 영어 표현 버튼은 강조된 배경/테두리로 시각적 피드백 제공

---

## 📌 기타 참고
GPT API 호출 시 meta.skipGlobalLoading: true 옵션을 통해 전역 로딩 차단 → 로컬 로딩 처리로 UX 향상

추천된 영어 표현은 추후 회고 저장 시 feelingEn 필드에 사용됨

selectedEnglish와 onEnglishSelect를 분리하여 상태 제어를 부모에 위임 → 재사용성 높음

