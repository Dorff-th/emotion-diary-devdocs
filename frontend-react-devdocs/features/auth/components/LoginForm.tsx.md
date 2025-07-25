📄 LoginForm.tsx
📁 위치
features/auth/components/LoginForm.tsx

🧭 역할
사용자로부터 아이디와 비밀번호를 입력받아 로그인 처리하는 폼 컴포넌트입니다.
로그인 성공 시 토큰 저장, 성공/실패 토스트 메시지 출력, 홈으로 리다이렉트까지 처리합니다.

🔗 주요 import 목록
| 항목               | 설명                             | 링크                                                              |
| ---------------- | ------------------------------ | --------------------------------------------------------------- |
| `login`          | 로그인 API 호출 함수                  | [authApi.tsx.md](../api/authApi.ts.md)                       |
| `useAuth`        | 로그인 후 토큰을 저장하는 커스텀 훅           | [AuthContext.tsx.md](../context/AuthContext.tsx.md)           |
| `useToastHelper` | 성공/에러 토스트 메시지를 쉽게 출력하기 위한 유틸 훅 | [toastHelper.ts.md](../../../features/toast/utils/toastHelper.ts.md) |
| `useNavigate`    | 리액트 라우터의 페이지 이동 함수             | -                                                               |



🧩 포함 컴포넌트 트리
text
복사
편집
LoginForm
├── <form onSubmit={handleLogin}>
│   ├── <input type="text" />   ← username 입력
│   ├── <input type="password" /> ← password 입력
│   └── <button type="submit">로그인</button>
📝 설명 및 주요 로직
useState로 username, password 상태 관리

handleLogin 함수에서:

기본 submit 이벤트 방지

login(username, password) 호출 → 응답에서 토큰 추출

saveToken(token)으로 전역 로그인 처리

성공 시 showSuccess, 실패 시 showError 호출

navigate('/')로 메인 페이지 이동

📌 기타 참고
UI는 TailwindCSS 기반으로 다크모드와 반응형 모두 대응

토스트 메시지는 사용자 경험을 높이는 핵심 요소로 포함

실제 로그인 API와 전역 상태관리(AuthContext) 연동이 깔끔하게 구성되어 있음

