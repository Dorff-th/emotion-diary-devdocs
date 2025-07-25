# 📄 CalendarSelector.tsx
## 📁 위치
features/calendar/components/CalendarSelector.tsx

---

## 🧭 역할
사용자가 연도 및 월을 드롭다운 형태로 직접 선택할 수 있게 하는 달력용 드롭다운 선택 UI 컴포넌트입니다.
선택된 날짜는 부모 컴포넌트(Calendar.tsx)로 전달되어 해당 월의 데이터를 다시 불러오는 데 사용됩니다.

---

## 🔗 주요 import 목록
| 항목         | 설명                     |
| ---------- | ---------------------- |
| `useState` | 드롭다운 열림 상태 관리용 React 훅 |


---

## 🧩 포함 컴포넌트 구조
```text
CalendarSelector
├── 버튼 영역 (현재 월/연도 표시, 클릭 시 드롭다운 토글)
└── 드롭다운
    ├── 연도 선택 select 박스
    └── 월 선택 select 박스
```
---    
## 📝 설명 및 주요 로직

props:

currentDate: 현재 선택된 기준 날짜 (Date 객체)

setCurrentDate: 날짜 상태를 상위에서 제어할 수 있도록 하는 setter 함수

isOpen: 드롭다운 토글 상태를 관리하는 로컬 상태

handleYearChange:

선택된 연도 값을 기준으로 현재 월을 유지하며 currentDate를 업데이트

handleMonthChange:

선택된 월 값을 기준으로 현재 연도를 유지하며 currentDate를 업데이트

버튼을 누르면 현재 연/월이 시각적으로 강조되어 표시되고, 드롭다운을 통해 직접 선택 가능

---

## 📌 기타 참고
TailwindCSS를 기반으로 한 스타일링이 적용되어 있으며, 사용자 친화적인 UI를 제공합니다.

월 이름은 toLocaleString('en-US', { month: 'long' })을 사용하여 영어로 표기됩니다 (예: July).

setIsOpen(false) 처리로 선택 후 자동으로 드롭다운이 닫히는 UX 개선이 반영되어 있습니다.

모바일 뷰에서도 드롭다운이 가운데 정렬되도록 translate-x-1/2 클래스를 활용합니다.