# 📄 UserHomePage.tsx
## 📁 위치
features/user/pages/UserHomePage.tsx

---

## 🧭 역할
사용자가 로그인 후 처음 진입하는 홈 화면으로, 상단에는 공통 Header를 표시하고 본문에는 오늘의 회고 요약(SummaryPage)을 보여주는 역할을 합니다.
다크모드 여부에 따라 배경 gradient 색상이 전환되며, 사용자 경험을 향상시킵니다.

---

## 🔗 주요 import 목록
| 항목            | 설명                  | 링크                                                              |
| ------------- | ------------------- | --------------------------------------------------------------- |
| `Header`      | 상단 네비게이션 컴포넌트       | [Header.tsx](../../layout/components/Header.tsx.md)          |
| `useTheme`    | 다크모드 여부를 제공하는 커스텀 훅 | [ThemeContext.tsx](../../../features/system/context/ThemeContext.tsx.md) |
| `SummaryPage` | 오늘 회고 요약 페이지 컴포넌트   | [SummaryPage.tsx](../../../features/summary/pages/SummaryPage.tsx.md)    |
| `clsx`        | 조건부 클래스명 유틸리티       | [clsx 공식문서](https://www.npmjs.com/package/clsx)                 |

---


## 🧩 포함 컴포넌트 트리
UserHomePage
├── Header
└── SummaryPage

---

## 📝 설명 및 주요 로직
useTheme() 커스텀 훅을 통해 현재 테마 모드(isDarkMode)를 가져옴

배경 스타일은 clsx를 통해 isDarkMode 값에 따라 다르게 적용됨

다크모드일 경우: from-gray-900 to-gray-800

일반모드일 경우: from-blue-100 to-white

메인 컨텐츠는 max-w-4xl로 중앙 정렬된 박스 안에 렌더링되며, 내부에 SummaryPage가 포함됨

---

## 📌 기타 참고
이 페이지는 사용자의 주요 요약 정보(감정, 회고 등)를 빠르게 확인할 수 있는 진입점입니다.

다크모드 상태에 따라 배경이 부드럽게 전환되도록 transition-colors와 duration-500 클래스를 활용합니다.

프로젝트 전체 스타일 일관성을 위해 Tailwind CSS 유틸리티 클래스가 중심적으로 사용됩니다.