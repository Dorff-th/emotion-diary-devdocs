# 📄 ThemeToggle.tsx
## 📁 위치
features/ui/components/ThemeToggle.tsx

---

## 🧭 역할
현재 다크모드/라이트모드 상태를 토글하는 버튼 컴포넌트입니다.
useTheme() 훅을 통해 전역 테마 상태를 가져오고, 버튼 클릭 시 테마를 전환합니다.

---

## 🔗 주요 import 목록
| 항목         | 설명                  | 링크                                                                   |
| ---------- | ------------------- | -------------------------------------------------------------------- |
| `useTheme` | 현재 테마 상태 및 토글 함수 제공 | [`ThemeContext.tsx.md`](../../system/context/ThemeContext.tsx.md) |

---


## 🧩 포함 컴포넌트 트리

ThemeToggle
└── <button onClick={toggleTheme}>
     └── ☀️ or 🌙 (현재 테마에 따라 아이콘 표시)

---     

## 📝 설명 및 주요 로직
useTheme() 커스텀 훅을 통해 isDarkMode, toggleTheme 값 가져옴

버튼 클릭 시 toggleTheme() 호출 → 다크/라이트 모드 전환

현재 모드에 따라 아이콘:

isDarkMode === true → ☀️ (라이트 아이콘 표시)

isDarkMode === false → 🌙 (다크 아이콘 표시)

## 📌 기타 참고
TailwindCSS의 dark: 클래스와 함께 전역 스타일이 자동 적용되도록 구성됨

이 버튼은 헤더 또는 로그인 박스 상단 등 다양한 곳에 삽입 가능

직관적인 이모지로 사용자 경험 향상에 기여