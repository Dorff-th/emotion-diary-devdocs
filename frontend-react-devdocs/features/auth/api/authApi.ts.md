# 📄 authApi.ts
# 📁 위치
features/auth/api/authApi.ts

# 🧭 역할
로그인과 로그아웃 기능을 처리하는 인증 관련 API 함수들을 정의한 모듈입니다.
로그인 시 axiosInstance를 사용하여 서버에 인증 요청을 보내고, 로그아웃 시 로컬 스토리지의 토큰을 제거합니다.

# 🔗 주요 import 목록
| 항목              | 설명                    | 링크                                                           |
| --------------- | --------------------- | ------------------------------------------------------------ |
| `axiosInstance` | 기본 설정이 적용된 Axios 인스턴스 | [`axiosInstance.ts`](../../../lib/axios/axiosInstance.ts.md) |


# 🧩 포함 함수 구조
authApi.ts
├── login(username, password) : Promise
└── logout() : void

# 📝 설명 및 주요 로직
📌 login(username: string, password: string): Promise
POST /auth/login 엔드포인트로 사용자명과 비밀번호 전송

응답으로 받은 data(예: 토큰 등)를 반환

예시 사용처: LoginForm.tsx에서 로그인 처리 시 사용

📌 logout(): void
로컬 스토리지에서 'token' 항목 제거

예시 사용처: 로그아웃 버튼 또는 인증 만료 시 클라이언트 정리

📌 기타 참고
이 모듈은 인증에 관한 로직만 분리하여 구성되어 있고, 상태 관리는 AuthContext 등 외부에서 처리

axiosInstance는 공통 API 요청 설정(예: baseURL, 헤더 등)을 포함하고 있음