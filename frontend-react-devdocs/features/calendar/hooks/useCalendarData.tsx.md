# 📄 useCalendarData.tsx
## 📁 위치
features/calendar/hooks/useCalendarData.tsx

---

## 🧭 역할
특정 연도와 월을 기반으로 달력에 표시할 날짜 배열을 생성하고, 각 날짜에 감정 관련 정보를 초기화하여 반환하는 사용자 정의 훅입니다.
이후 API 연동 또는 비즈니스 로직이 추가되기 위한 기본 틀로 사용됩니다.

---

## 🔗 주요 import 목록
| 항목                | 설명                                    | 링크                                                     |
| ----------------- | ------------------------------------- | ------------------------------------------------------ |
| `getDaysInMonth`  | 특정 연/월의 날짜 리스트(YYYY-MM-DD 문자열 배열)를 반환 | [calendarUtils.ts](../../../utils/calendarUtils.ts.md) |
| `CalendarDayData` | 날짜별 감정 데이터를 위한 타입 정의                  | [calendar.types.ts](../types/calendar.types.ts.md)     |


---

## 🧩 포함 훅 구조
```text
useCalendarData (입력: year, month)
├── useState: calendarData 상태 초기화
├── useEffect: year/month 변경 시 날짜 목록 계산
│   ├── getDaysInMonth 호출
│   └── 날짜별 기본 데이터 map 구성
└── return: { calendarData }
```
---

## 📝 설명 및 주요 로직
입력값: year, month

getDaysInMonth(year, month): 해당 월의 모든 날짜를 YYYY-MM-DD 문자열 배열로 반환합니다.

각 날짜에 대해 초기 감정 스코어(emotionScore)와 이모지(emotionEmoji)는 undefined로 설정됩니다.

추후 API 연동 등을 통해 실제 감정 데이터를 주입할 수 있도록 확장 가능한 구조입니다.

결과는 calendarData 배열로 반환되며, 이 배열은 캘린더 UI 렌더링에 활용됩니다.

---

## 📌 기타 참고
이 훅은 추후 emotionScore, emoji 값을 실제 데이터로 채우기 위해 API 통합이 필요합니다.

getDaysInMonth 유틸 함수는 윤년이나 월별 일 수를 자동으로 계산해줍니다.

타입은 CalendarDayData[]로 명시되어 있어, 타입 기반 자동완성 및 정적 분석에 유리합니다.

