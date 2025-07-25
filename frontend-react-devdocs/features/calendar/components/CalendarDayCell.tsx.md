## 📄 CalendarDayCell.tsx
# 📁 위치
features/calendar/components/CalendarDayCell.tsx

---

## 🧭 역할
달력에서 개별 날짜 셀을 렌더링하는 컴포넌트로, 해당 날짜에 작성된 회고 기록을 기반으로 감정 이모지 및 상태를 표시합니다.
날짜 클릭, 오늘 날짜 강조, 요약 여부, 요일에 따른 색상 처리 등 다양한 시각적 요소를 포함합니다.

---

## 🔗 주요 import 목록
| 항목                                | 설명                      | 링크                                                  |
| --------------------------------- | ----------------------- | --------------------------------------------------- |
| `emotionEmojiMap`, `EmotionLevel` | 감정 점수에 따라 이모지를 매핑하는 Map | [emotionMap.ts](../../diary/types/emotionMap.ts.md) |
| `DiaryEntry`                      | 회고 데이터 타입 정의            | [calendarApi.ts](../api/calendarApi.ts.md)          |


---

## 🧩 포함 컴포넌트 구조
```text
CalendarDayCell
├── fullDate 계산 (YYYY-MM-DD)
├── 감정 점수 평균 계산
│   └── emoji 이모지 선택
└── <div>로 날짜 셀 구성
    ├── 클릭 가능 여부
    ├── 감정 이모지 표시
    └── 요약 아이콘 (있을 경우)
```

## 📝 설명 및 주요 로직
입력 props:

date, year, month → fullDate 문자열로 조합

diaryEntries → 해당 날짜의 회고 목록

averageScore:

회고 감정 점수 평균을 1~5 범위 내로 제한하여 계산

emotion:

emotionEmojiMap에서 평균 점수에 해당하는 이모지를 가져옴

isClickable:

감정 데이터가 있는 경우에만 셀을 클릭 가능하게 설정

요일 색상 처리:

일요일은 빨간색, 토요일은 파란색으로 표시

---

## 📌 기타 참고
다크모드 및 테마에 따라 색상 변경을 위해 Tailwind clsx 조합이 적용됨

onClick 핸들러는 날짜 셀 클릭 시 외부에서 모달 등을 열 수 있도록 지원함

hasSummary 값에 따라 아이콘이 나타나거나 강조될 수 있는 여지가 있음 (추후 확장 가능)

