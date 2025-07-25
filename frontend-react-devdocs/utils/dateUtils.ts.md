# 📄 dateUtils.ts
## 📁 위치
utils/dateUtils.ts

---

## 🧭 역할
감정 통계에서 사용되는 날짜 필터링 로직을 도와주는 유틸 함수 모음입니다.
선택한 기간 옵션(PeriodOption)에 따라 시작일과 종료일을 계산하는 함수 getDateRange()를 제공합니다.

---

## 🔗 주요 import 목록
항목	설명	링크
| 항목                                                                            | 설명                   | 링크                                                                    |
| ----------------------------------------------------------------------------- | -------------------- | --------------------------------------------------------------------- |
| `startOfWeek`, `endOfWeek`, `startOfMonth`, `endOfMonth`, `subDays`, `format` | 날짜 계산 및 포맷을 위한 유틸 함수 | [date-fns 공식문서](https://date-fns.org/)                                |
| `PeriodOption`                                                                | 기간 옵션에 대한 타입 정의      | [statisticsTypes.ts](../features/statistics/types/statisticsTypes.ts) |


---

## 🧩 포함 함수 트리
```text
getDateRange(option: PeriodOption): [string, string]
├── this-week: 이번 주의 시작 ~ 끝 날짜
├── this-month: 이번 달의 시작 ~ 끝 날짜
├── last-7-days: 오늘 기준 7일 전 ~ 오늘까지
└── default: 빈 문자열 배열 반환 (ex: 사용자 지정용)
```
---

## 📝 설명 및 주요 로직
getDateRange(option) 함수는 PeriodOption 값에 따라 yyyy-MM-dd 형식의 시작일/종료일 문자열 배열을 반환합니다.

this-week의 경우 주의 시작을 월요일로 지정 ({ weekStartsOn: 1 }).

last-7-days는 오늘 포함 과거 6일 전까지 범위 지정.

default 케이스는 ['', ''] 반환 → 사용자 정의(Custom Range)용 예외 처리로 활용 가능.

---

## 📌 기타 참고
날짜 관련 라이브러리로 date-fns를 일관되게 사용하고 있어 유지보수가 용이합니다.

상위에서 사용하는 페이지: EmotionStatsPage.tsx

사용자 지정 기간 로직은 추후 커스터마이징 또는 범위 유효성 검사가 필요할 수 있습니다.

