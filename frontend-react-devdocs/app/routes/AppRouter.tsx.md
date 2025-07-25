# AppRouter.tsx

> Emotion Diary App의 라우팅을 담당하는 컴포넌트로, 사용자/관리자 페이지 구성을 포함한 라우터 트리 정의를 담당합니다.

---

## 📁 위치
`app/routes/AppRouter.tsx`

---

## 🧩 주요 역할

- `react-router-dom`의 `createBrowserRouter`를 사용하여 앱 전체 라우팅 설정
- 라우트 보호를 위해 `PrivateRoute` 구성 사용
- 에러 페이지(`NotFoundPage`) 핸들링
- 사용자 페이지와 관리자 페이지를 라우팅으로 분리

---

## 🧱 사용 중인 컴포넌트 / 라우트

- [`LoginPage.tsx.md`](../../features/auth/pages/LoginPage.tsx.md)
- [`UserHomePage.tsx.md`](../../features/user/pages/UserHomePage.tsx.md)
- [`DiaryInputPage.tsx.md`](../../features/diary/pages/DiaryInputPage.tsx.md)
- [`DiaryListPage.tsx.md`](../../features/diary/pages/DiaryListPage.tsx.md)
- [`DiaryInsightsPage.tsx.md`](../../features/statistics/pages/EmotionStatsPage.tsx.md)
- [`SearchResultPage.tsx.md`](../../features/search/pages/SearchResultPage.tsx.md)
- [`CalendarPage.tsx.md`](../../features/calendar/pages/CalendarPage.tsx.md)
- [`PrivateRoute.tsx.md`](../routes/PrivateRoute.tsx.md)
- [`NotFoundPage.tsx.md`](../../features/layout/pages/NotFoundPage.tsx.md)

---

## 📜 주요 라우팅 구조

```tsx
const router = createBrowserRouter([
  {
    path: '/',
    element: <PrivateRoute><UserHomePage /></PrivateRoute>,
  },
  {
    path: '/login',
    element: <LoginPage />,
  },
  {
    path: '/diary',
    element: <PrivateRoute><DiaryInputPage /></PrivateRoute>,
  },
  {
    path: '/list',
    element: <PrivateRoute><DiaryListPage /></PrivateRoute>,
  },
  {
    path: '/insights',
    element: <PrivateRoute><DiaryInsightsPage /></PrivateRoute>,
  },
  {
    path: '/search',
    element: <PrivateRoute><SearchResultPage /></PrivateRoute>,
  },
  {
    path: '/calendar',
    element: <PrivateRoute><CalendarPage /></PrivateRoute>,
  },
  {
    path: '*',
    element: <NotFoundPage />,
  }
]);
🌐 export

export default function AppRouter() {
  return <RouterProvider router={router} />;
}
🔗 연관 문서
PrivateRoute.tsx.md

LoginPage.tsx.md

UserHomePage.tsx.md

DiaryInputPage.tsx.md

DiaryListPage.tsx.md

DiaryInsightsPage.tsx.md

SearchResultPage.tsx.md

CalendarPage.tsx.md

NotFoundPage.tsx.md

✅ 완료된 기능
 전체 라우팅 구성

 로그인/비로그인에 따른 보호된 라우트 구성

 404 Not Found 라우트 처리

📌 TODO
 관리자 페이지 전용 라우팅 보호 추가 (예: /admin)

 Suspense 및 LazyRoute로 최적화 가능성 검토

 라우팅 전환 시 로딩 처리 개선