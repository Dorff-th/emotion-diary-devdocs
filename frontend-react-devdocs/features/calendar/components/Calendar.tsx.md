# 📄 Calendar.tsx
## 📁 위치
features/calendar/components/Calendar.tsx

---

## 🧭 역할
현재 월의 감정 & 회고 기록 데이터를 기반으로 달력을 렌더링하고, 날짜별 회고 내용을 시각적으로 보여주는 핵심 달력 컴포넌트입니다.
월 이동, 날짜 선택, 상세 모달 보기 등의 상호작용이 포함되어 있습니다.

---

## 🔗 주요 import 목록
| 항목                      | 설명                  | 링크                                                                               |
| ----------------------- | ------------------- | -------------------------------------------------------------------------------- |
| `useCalendarData`       | 달력 데이터 및 날짜 관련 유틸 훅 | [useCalendarData.ts](../../calendar/hooks/useCalendarData.tsx.md)                             |
| `CalendarDayCell`       | 개별 날짜 셀 컴포넌트        | [CalendarDayCell.tsx](./CalendarDayCell.tsx.md)                                  |
| `CalendarSelector`      | 연/월 선택 드롭다운 컴포넌트    | [CalendarSelector.tsx](./CalendarSelector.tsx.md)                                |
| `DiaryListForDateModal` | 특정 날짜의 회고 목록 모달     | [DiaryListForDateModal.tsx](../../diary/components/DiaryListForDateModal.tsx.md) |
| `fetchMonthDiaryList`   | 월간 회고 데이터 불러오기 API  | [calendarApi.ts](../api/calendarApi.ts.md)                                       |


---

## 🧩 포함 컴포넌트 트리
```text
Calendar
├── CalendarSelector
├── 날짜 셀 (반복 렌더링)
│   └── CalendarDayCell (각 일자별 회고 상태 표시)
└── DiaryListForDateModal (선택 날짜 클릭 시 회고 모달 팝업)
```

---

## 📝 설명 및 주요 로직
currentDate: 현재 기준이 되는 날짜 상태이며, 월 변경 시 함께 갱신됩니다.

startDayStr: API 호출 시 사용할 YYYY-MM-DD 형식의 월 시작일 문자열입니다.

useEffect: fetchMonthDiaryList()를 통해 해당 월의 회고 데이터를 API에서 불러옵니다.

diaryMapByDate: useMemo()를 통해 날짜별 회고 데이터를 Map 형태로 변환하여 렌더링 효율성을 높입니다.

CalendarDayCell: 일자별 회고 상태 표시 (예: 작성 여부, 감정 상태 등)

DiaryListForDateModal: 특정 날짜 클릭 시 해당 날짜의 회고를 모달로 표시합니다.

handlePrevMonth, handleNextMonth: 월 단위 이동 처리

---

## 📌 기타 참고
다크모드 대응 및 UI 애니메이션은 TailwindCSS 기반으로 처리되고 있습니다.

날짜 셀 렌더링에 따라 추가 스타일이나 마커가 포함될 수 있으며, 감정이나 회고 유무에 따라 시각적으로 표시됩니다.

각종 상태는 내부에서 useState로 관리되며, context를 사용하지 않고 로컬에서 처리합니다.

