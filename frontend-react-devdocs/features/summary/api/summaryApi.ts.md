# 📄 summaryApi.ts
## 📁 위치
features/summary/api/summaryApi.ts

---

## 🧭 역할
오늘 날짜의 회고 요약 데이터 및 GPT 요약 결과를 불러오는 API 호출 함수들을 정의한 파일입니다.
axios 인스턴스를 활용하여 백엔드 REST API와 통신합니다.

## 🔗 주요 import 목록
| 항목              | 설명                | 링크                                                         |
| --------------- | ----------------- | ---------------------------------------------------------- |
| `axiosInstance` | 설정된 공통 Axios 인스턴스 | [axiosInstance.ts](../../../lib/axios/axiosInstance.ts.md) |
| `SummaryData`   | 회고 요약 데이터 타입      | [SummaryTypes.ts](../types/SummaryTypes.ts.md)             |

---


## 🧩 포함 함수 구조
text
복사
편집
summaryApi.ts
├── fetchTodaySummary()         // 오늘 입력된 회고 중 가장 최근 1개를 반환
└── fetchTodayGptSummary()      // 오늘 회고의 GPT 요약만 별도로 반환

---

## 📝 설명 및 주요 로직
1. fetchTodaySummary

export const fetchTodaySummary = async (): Promise<SummaryData> => {
  const res = await axiosInstance.get<SummaryData>('/user/summary/today');
  return res.data;
};

오늘 작성된 회고 중 가장 최근 1개의 데이터만을 반환

기존의 "오늘 날짜 전체 요약"에서 변경됨 (주석 참고)

반환값 타입: SummaryData

2. fetchTodayGptSummary

export const fetchTodayGptSummary = async (): Promise<{ summary: string }> => {
  const res = await axiosInstance.get('/user/gpt-summary/today');
  return res.data;
};
GPT가 생성한 요약 텍스트만 별도로 가져옴 (summary 필드)

사용 목적: 요약만 필요할 때의 최적화된 경로 제공

---

## 📌 기타 참고
이 API 함수들은 useSummaryData.ts, SummaryCard.tsx, FeedbackCard.tsx 등에서 사용될 수 있으며, 각 컴포넌트에서 필요한 데이터만 분리 호출할 수 있도록 구성되어 있음

/user/summary/today와 /user/gpt-summary/today는 기능이 비슷하지만 반환값 형태가 다름 → 혼동 주의!

