# 📄 Header.tsx
## 📁 위치
features/layout/components/Header.tsx

---

## 🧭 역할
앱 상단에 위치하는 공통 헤더 컴포넌트입니다.
사용자 프로필 버튼, 네비게이션 메뉴, 다크모드 토글, 로그아웃 기능, 검색 입력창을 포함하고 있으며, 사용자 경험을 고려한 UI/UX를 제공합니다.

## 🔗 주요 import 목록
| 항목                                   | 설명                    | 링크                                                           |
| ------------------------------------ | --------------------- | ------------------------------------------------------------ |
| `useAuth`                            | 인증 상태 관리 및 로그아웃 기능 제공 | [AuthContext.tsx](../../../features/auth/context/AuthContext.tsx.md)  |
| `useToastHelper`                     | 사용자 알림 표시를 위한 커스텀 훅   | [toastHelper.ts](../../../features/toast/utils/toastHelper.ts.md)     |
| `ThemeToggle`                        | 다크모드 토글 버튼 컴포넌트       | [ThemeToggle.tsx](../../../features/ui/components/ThemeToggle.tsx.md) |
| `bunnyIcon`                          | 프로필 이미지로 사용되는 캐릭터 이미지 | `/assets/characters/loading_bunny_gpt.png`                   |
| `Link`, `useLocation`, `useNavigate` | React Router 기능       | [react-router-dom](https://reactrouter.com/en/main)          |
| `clsx`                               | 조건부 클래스명 유틸리티         | [clsx 공식문서](https://www.npmjs.com/package/clsx)              |

---

## 🧩 포함 컴포넌트 트리
```text
Header
├── 버튼 (프로필 이미지)
├── 메뉴 리스트 (홈 / 회고 쓰기 / 달력 / 목록 / 분석)
├── 검색창
└── ThemeToggle
```
---

## 📝 설명 및 주요 로직
useAuth()로부터 logout 함수를 받아와 로그아웃 시 호출하며, 토스트 메시지를 함께 표시

useLocation()을 통해 현재 경로를 확인하고, 메뉴 항목과 일치하는 경우 스타일 강조

useNavigate()를 사용해 검색어를 포함한 경로로 이동 (page=1, size=10 기본 포함)

메뉴는 🏠 홈, ✍️ 회고 쓰기, 📆 회고 달력, 📜 회고 목록, 📊 감정 분석으로 구성

ThemeToggle 컴포넌트를 통해 다크모드 전환 가능

Tailwind CSS의 유틸리티 클래스를 적극 사용해 반응형, 다크모드 등을 지원

---

## 📌 기타 참고
프로필 버튼 클릭 시 아직 기능은 없으나 콘솔 로그 출력 → 추후 마이페이지 이동 기능으로 확장 가능

검색어 입력 후 엔터를 누르면 쿼리 문자열과 함께 검색결과 페이지로 이동

다크모드 적용 시 배경색 및 구분선 등 다양한 요소가 함께 변경되어 일관된 UX 제공