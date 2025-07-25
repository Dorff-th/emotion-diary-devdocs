# 📄 gptSummaryApi.ts
## 📁 위치
features/gpt/api/gptSummaryApi.ts

---

## 🧭 역할
특정 날짜에 작성된 회고 기록을 기반으로 GPT 요약을 생성하기 위한 API 호출 함수를 정의합니다.
프론트엔드에서 GPT 기반 요약 결과를 받아올 때 사용됩니다.

---

## 🔗 주요 export 목록
| 함수명                        | 설명                                          |
| -------------------------- | ------------------------------------------- |
| `generateGptSummary(date)` | 날짜(`YYYY-MM-DD`)를 기준으로 해당 날짜 회고 내용을 GPT로 요약 |


---

## 🧩 함수 구조
```ts
function generateGptSummary(date: string): Promise<string>
├── POST /user/diary/gpt-summary
├── 요청 바디: { date }
└── 응답: { summary: string }
```
---
## 📝 설명 및 주요 로직
입력값: date (형식: "YYYY-MM-DD")

내부적으로 axiosInstance를 통해 POST 요청을 보냅니다.

요청 경로: /user/diary/gpt-summary

요청 바디에 날짜를 포함: { date: "2025-07-25" }

응답 데이터에서 summary 필드를 추출하여 문자열로 반환

---

## 📌 기타 참고
이 함수는 DiaryListForDateModal.tsx에서 사용되며, 사용자가 버튼을 클릭하여 GPT 요약을 수동으로 생성할 수 있게 합니다.

백엔드에서 GPT API(OpenAI 등)를 호출하고, 그 결과를 summary 필드에 담아 반환하는 구조로 설계되어 있어야 합니다.

오류 처리(try/catch)는 호출하는 컴포넌트 단에서 수행합니다.

Axios 인스턴스는 인증 토큰 등이 포함된 공통 설정이 적용된 인스턴스를 사용합니다.

