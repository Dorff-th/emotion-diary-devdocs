# 📄 useSummaryData.ts
## 📁 위치
features/summary/hooks/useSummaryData.ts

---

## 🧭 역할
오늘 날짜에 해당하는 회고 요약 데이터를 API로부터 비동기적으로 가져오는 커스텀 훅입니다.
데이터를 호출하는 로직과 로딩 상태를 함께 관리하여, 요약 관련 컴포넌트들이 간결하게 데이터를 사용할 수 있도록 도와줍니다.

---

## 🔗 주요 import 목록
| 항목                      | 설명                            | 링크                                              |
| ----------------------- | ----------------------------- | ----------------------------------------------- |
| `fetchTodaySummary`     | 오늘 날짜의 회고 요약 데이터를 가져오는 API 함수 | [summaryApi.ts](../api/summaryApi.ts.md)        |
| `SummaryData`           | 회고 요약 데이터 타입 정의               | [SummaryTypes.ts](../types/SummaryTypes.ts.md)  |
| `useState`, `useEffect` | React 기본 훅                    | [React 공식문서](https://react.dev/reference/react) |

---


## 🧩 포함 구조

useSummaryData
├── fetchTodaySummary()
├── useState(summary, loading)
└── useEffect(데이터 fetch 및 상태 갱신)

---

## 📝 설명 및 주요 로직
summary: 회고 요약 데이터를 담는 상태 (초기값: null)

loading: 로딩 여부를 나타내는 boolean 상태 (초기값: true)

컴포넌트가 마운트되면 useEffect를 통해 fetchTodaySummary()를 호출하고, 성공 시 summary에 저장

API 호출이 완료되면 성공/실패 여부와 관계없이 loading을 false로 변경

useEffect(() => {
  fetchTodaySummary()
    .then(data => setSummary(data))
    .finally(() => setLoading(false));
}, []);

반환값은 { summary, loading } 형태로, 사용하는 컴포넌트에서는 간단히 해당 데이터를 활용 가능

---

## 📌 기타 참고
fetchTodaySummary는 백엔드에서 오늘 날짜(LocalDate.now()) 기준 회고 데이터를 가져오는 API로 연결되어 있어야 함

이 훅은 SummaryPage.tsx에서 직접 사용되며, 로딩 상태에 따른 조건부 렌더링도 함께 구성됨

다음 문서화 대상이 있다면 알려줘! 예: summaryApi.ts, SummaryTypes.ts, TodayEmotionCard.tsx 등.
이 문서 역시 .md 파일로 출력해줄 수 있어.