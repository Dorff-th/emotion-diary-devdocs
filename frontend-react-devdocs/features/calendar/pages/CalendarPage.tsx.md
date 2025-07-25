## 📄 CalendarPage.tsx
# 📁 위치
features/calendar/pages/CalendarPage.tsx

---

# 🧭 역할
사용자가 감정 및 회고 입력 여부를 한눈에 확인할 수 있도록 달력을 시각적으로 제공하는 페이지입니다.
상단에는 Header가 표시되고, 중앙에는 Calendar 컴포넌트가 렌더링되어 월별로 회고 상태를 확인할 수 있습니다.

---

## 🔗 주요 import 목록
| 항목         | 설명                         | 링크                                                  |
| ---------- | -------------------------- | --------------------------------------------------- |
| `Header`   | 전체 앱의 공통 상단 헤더             | [Header.tsx](../../layout/components/Header.tsx.md) |
| `Calendar` | 사용자 감정/회고 상태를 보여주는 달력 컴포넌트 | [Calendar.tsx](../components/Calendar.tsx.md)       |


## 🧩 포함 컴포넌트 트리
```text
CalendarPage
├── Header
└── div (배경 및 섹션 스타일)
    └── main
        └── div (카드 형태 컨테이너)
            ├── h2 (페이지 제목)
            ├── p (설명 텍스트)
            └── Calendar
```

---

## 📝 설명 및 주요 로직
Header 컴포넌트를 통해 앱의 상단 고정 헤더를 렌더링합니다.

TailwindCSS로 배경 그라데이션 및 다크모드 대응이 적용된 페이지 레이아웃을 구성합니다.

Calendar 컴포넌트를 통해 월별 회고 여부를 시각적으로 확인할 수 있는 UI를 제공합니다.

---

## 📌 기타 참고
Calendar 컴포넌트는 사용자 회고 여부를 날짜별로 확인할 수 있도록 시각화되어 있으며, 별도의 API 연동 또는 context 기반 상태를 내부에서 관리하고 있을 가능성이 큽니다.

배경 및 전환 효과는 다크모드에서도 부드럽게 동작하도록 TailwindCSS transition-colors 클래스를 활용하고 있습니다.