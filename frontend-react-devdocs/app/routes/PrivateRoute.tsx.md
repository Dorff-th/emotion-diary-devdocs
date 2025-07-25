# PrivateRoute.tsx

> 인증되지 않은 사용자가 접근할 수 없도록 보호된 라우트를 구성하는 컴포넌트입니다.  
로그인 여부를 검사하여 미인증 사용자는 `/login`으로 리디렉션합니다.

---

## 📁 위치
`app/routes/PrivateRoute.tsx`

---

## 🧩 주요 역할

- 인증 상태(`isLoggedIn`)를 확인하여 라우트 접근을 보호
- 로그인되지 않은 경우 로그인 페이지로 강제 이동
- 로그인된 경우에는 자식 컴포넌트를 정상적으로 렌더링

---

## 🧱 사용 중인 훅/모듈

- [`AuthContext.tsx.md`](../../features/auth/context/AuthContext.tsx.md)
- [`Navigate`](https://reactrouter.com/en/main/components/navigate) – React Router 공식 컴포넌트


---

## 📜 주요 코드

```tsx
import { useAuth } from '@/features/auth/hooks/useAuth';
import { Navigate } from 'react-router-dom';

interface Props {
  children: React.ReactNode;
}

export default function PrivateRoute({ children }: Props) {
  const { isLoggedIn } = useAuth();

  if (!isLoggedIn) {
    return <Navigate to="/login" replace />;
  }

  return <>{children}</>;
}
🔐 사용 예시

{
  path: '/diary',
  element: (
    <PrivateRoute>
      <DiaryInputPage />
    </PrivateRoute>
  ),
}
🔗 연관 문서
useAuth.tsx.md

AppRouter.tsx.md

✅ 완료된 기능
 로그인 여부에 따른 라우팅 제어

 미인증 시 /login으로 리디렉션

📌 TODO
 관리자 전용 권한(role === 'ADMIN')에 따른 추가 보호 로직 도입 가능

 redirectAfterLogin 등 리디렉션 히스토리 저장 기능 고려

