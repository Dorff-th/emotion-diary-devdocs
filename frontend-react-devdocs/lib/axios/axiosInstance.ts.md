# 📄 axiosInstance.ts
## 📁 위치
lib/axios/axiosInstance.ts

---

## 🧭 역할
앱 전역에서 사용하는 Axios 인스턴스를 생성하고,
공통 요청/응답 인터셉터를 설정하여 인증 토큰 자동 첨부, 전역 로딩 처리,
인증 실패 시 자동 로그아웃 등 클라이언트 전반의 API 처리 흐름을 관리합니다.

---

## 🔗 주요 import 목록
| 항목                  | 설명                                   | 링크                                                                           |
| ------------------- | ------------------------------------ | ---------------------------------------------------------------------------- |
| `getLoadingControl` | 전역 로딩 상태를 제어하는 유틸 함수                 | [`LoadingControl.ts`](../../features/system/context/LoadingControl.tsx.md) |
| `useAuth`           | 사용자 인증 상태 관리 훅 (사용되고 있지만 직접 호출되지 않음) | [`AuthContext.tsx.md`](../../features/auth/context/AuthContext.tsx.md)    |
| `useToastHelper`    | 전역 토스트 유틸 (직접 사용되진 않음)               | [`toastHelper.ts.md`](../../features/toast/utils/toastHelper.ts.md)     |

## 🧩 포함 로직 구조
```text
axiosInstance
├── baseURL, timeout 설정
├── request interceptor
│   ├── 토큰 자동 첨부
│   └── 로딩 시작 (getLoadingControl().showLoading)
├── response interceptor
│   ├── 로딩 종료 (getLoadingControl().hideLoading)
│   └── 401/403 오류 시 자동 로그아웃 + alert + redirect
```
---

## 📝 설명 및 주요 로직
### ✅ 요청 인터셉터
localStorage에서 token을 가져와 Authorization 헤더에 자동 추가

meta.skipGlobalLoading이 없으면 전역 로딩 표시

### ✅ 응답 인터셉터
요청 완료 후 전역 로딩 해제

401 또는 403 에러 시:

토큰 삭제

로그아웃 알림 (alert)

/login 페이지로 강제 이동

---

## 📌 기타 참고
axiosInstance는 다른 API 모듈(ex. authApi.ts)에서 재사용됨

meta.skipGlobalLoading은 특정 요청에서 로딩 생략이 필요할 때 사용 가능

useAuth, useToastHelper는 현재 코드에선 미사용(import만 되어 있음)