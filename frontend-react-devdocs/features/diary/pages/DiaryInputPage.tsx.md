# 📄 DiaryInputPage.tsx
## 📁 위치
features/diary/pages/DiaryInputPage.tsx

---

## 🧭 역할
오늘의 감정과 회고 내용을 입력하는 DiaryForm 컴포넌트를 포함한 페이지입니다. 다크모드와 라이트모드에 따라 배경 그라데이션이 달라지며, 상단에는 공통 Header를 표시합니다.

---

## 🔗 주요 import 목록
| 항목          | 설명                                          | 링크                                                           |
| ----------- | ------------------------------------------- | ------------------------------------------------------------ |
| `Header`    | 페이지 상단에 공통 헤더를 렌더링합니다.                      | [Header.tsx](../../layout/components/Header.tsx.md)          |
| `useTheme`  | 테마(다크모드/라이트모드) 상태를 관리하는 Context 훅입니다.       | [ThemeContext.tsx](../../system/context/ThemeContext.tsx.md) |
| `clsx`      | 조건부 className 처리를 도와주는 유틸리티 라이브러리입니다.       | 외부 라이브러리                                                     |
| `DiaryForm` | 감정 점수, 습관 체크, 회고 일기 등 입력 폼을 포함한 주요 컴포넌트입니다. | [DiaryForm.tsx](../components/DiaryForm.tsx.md)              |


## 🧩 포함 컴포넌트 트리
```text
DiaryInputPage
├── Header
└── main
    └── div (Container)
        └── DiaryForm
```

---

## 📝 설명 및 주요 로직
useTheme 훅을 사용하여 현재 다크모드 상태를 확인하고, 이에 따라 배경 그라데이션 색상을 조정합니다.

clsx 유틸을 통해 조건부 스타일을 간결하게 처리합니다.

Header 컴포넌트를 통해 페이지 상단 메뉴를 고정 구성합니다.

본문 영역에는 DiaryForm 컴포넌트를 사용하여 감정, 습관, 회고 내용을 입력받습니다.

Tailwind CSS 클래스를 활용해 반응형 UI와 다크모드 대응이 잘 구성되어 있습니다.

---

### 📌 기타 참고
향후 DiaryForm 내부 컴포넌트들이 확장되면 이 페이지는 그 중심 입력 허브 역할을 하게 됩니다.

Header는 전역적으로 사용되며, UI 일관성을 제공합니다.

useTheme는 앱 전체 테마 상태를 공유하므로, ThemeProvider가 루트에 설정되어 있어야 정상 동작합니다.