# 📄 ThemeContext.tsx
## 📁 위치
features/system/context/ThemeContext.tsx

---

## 🧭 역할
다크모드와 라이트모드 전환을 위한 전역 테마 상태를 관리하는 Context입니다.
useTheme() 훅을 통해 현재 테마 상태와 테마 전환 함수를 전역에서 사용할 수 있게 합니다.

---

## 🔗 주요 import 목록
| 항목                                                     | 설명                          | 링크 |
| ------------------------------------------------------ | --------------------------- | -- |
| `useState`, `useEffect`, `createContext`, `useContext` | React 기본 훅 및 Context API 사용 | -  |
| `ReactNode`                                            | Provider의 children 타입 정의    | -  |

---


## 🧩 포함 구조
```text
ThemeProvider
└── children
    └── useTheme()로 테마 상태 사용 가능
```    

## 📝 설명 및 주요 로직
## ✅ ThemeProvider
초기값은 localStorage.getItem('theme')을 통해 'dark' 여부를 확인

toggleTheme() 호출 시:

상태 반전 (true <-> false)

localStorage에 저장 ('dark' 또는 'light')

useEffect()로 isDarkMode 변화 시 document.documentElement.classList.toggle('dark') 호출
→ TailwindCSS의 dark: 클래스가 활성화됨

## ✅ useTheme()
ThemeContext에 접근하여 현재 테마 상태 및 토글 함수 반환

ThemeProvider 외부에서 호출할 경우 예외 발생

---

## 📌 기타 참고
TailwindCSS의 dark 모드 시스템을 기반으로 구성

ThemeToggle.tsx 등에서 사용되어 사용자 테마 직접 변경 가능

localStorage를 통해 사용자 설정이 브라우저에 영구 저장됨

