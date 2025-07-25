# 📄 AuthContext.tsx
## 📁 위치
features/auth/context/AuthContext.tsx

---

## 🧭 역할
사용자 인증 상태를 전역에서 관리하는 React Context입니다.
로그인/로그아웃 처리, 토큰 저장, 토큰 만료 체크 등의 기능을 제공하며,
useAuth() 훅으로 전역 인증 상태를 사용할 수 있게 합니다.

---

## 🔗 주요 import 목록
| 항목            | 설명                   | 링크         |
| ------------- | -------------------- | ---------- |
| `useNavigate` | 페이지 이동을 위한 리액트 라우터 훅 | (외부 라이브러리) |

---


## 🧩 포함 컴포넌트 트리
```text
AuthProvider
└── children
    └── useAuth()로 context 접근 가능
```

---

## 📝 설명 및 주요 로직
### ✅ AuthContextType
전역으로 공유할 인증 정보 구조 정의:

token, isAuthenticated, login(), logout() 포함

### ✅ AuthProvider
초기 토큰 상태는 localStorage.getItem('token')으로 설정

login(token) → 토큰 저장 + 상태 업데이트

logout() → 토큰 삭제 + 상태 초기화

### ✅ 토큰 만료 확인
isTokenExpired() 함수에서 JWT의 payload를 디코딩

exp(만료 시간) 필드와 현재 시간을 비교

만료된 경우 자동 로그아웃 처리

### ✅ useEffect 로직
앱 초기 진입 시 localStorage.getItem('accessToken') 확인

없거나 만료됐으면 → logoutFn()

유효하면 → isAuthenticated를 true로 설정

### ✅ useAuth() 훅
useContext()를 통해 AuthContext를 간편하게 사용할 수 있도록 래핑

context가 null일 경우 에러를 던져 예외 상황 대비

## 📌 기타 참고
token 저장 키가 token과 accessToken이 혼용됨
→ 일관성을 유지하거나 리팩토링이 필요할 수 있음

AuthProvider는 루트 컴포넌트(App 등)에서 전체를 감싸야 작동함

다른 API 호출(axiosInstance)과 유기적으로 연결됨