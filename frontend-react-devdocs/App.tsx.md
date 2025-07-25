# App.tsx

> Emotion Diary App의 루트 컴포넌트. 전역 스타일, 테마 설정, 로딩/토스트 상태 관리, 인증 컨텍스트를 설정하며 라우팅을 연결합니다.

---

## 📁 위치
`App.tsx`

---

## 🧩 주요 역할

- 앱 전역 컨텍스트 구성 (`Theme`, `Toast`, `Loading`, `Auth`)
- 라우팅 설정을 `AppRouter`를 통해 연결
- 전역 로딩 UI 및 토스트 메시지 컨테이너 삽입

---

## 🧱 사용 중인 컴포넌트/Provider

- [`AuthProvider`](./features/auth/context/AuthContext.tsx.md)
- [`AppRouter`](./app/routes/AppRouter.md)
- [`EmotionToastProvider`](./features/toast/context/EmotionToastProvider.tsx.md)
- [`EmotionToastContainer`](./features/toast/components/EmotionToastContainer.tsx.md)
- [`LoadingProvider`](./features/system/context/LoadingContext.tsx.md)
- [`LoadingOverlay`](./features/ui/components/LoadingOverlay.tsx.md)
- [`ThemeProvider`](./features/system/context/ThemeContext.tsx.md)

---

## 📜 주요 코드 구조

```tsx
function App() {
  return (
    <ThemeProvider>
      <EmotionToastProvider>
        <LoadingProvider>
          <AuthProvider>
            <AppRouter />
            <EmotionToastContainer />
            <LoadingOverlay />
          </AuthProvider>
        </LoadingProvider>
      </EmotionToastProvider>
    </ThemeProvider>
  );
}
ThemeProvider: 전역 다크모드/라이트모드 관리

EmotionToastProvider: 커스텀 토스트 전역 관리

LoadingProvider: API 로딩 등 글로벌 로딩 상태 관리

AuthProvider: 로그인 사용자 상태 및 인증 컨텍스트

AppRouter: 실제 라우팅 설정

EmotionToastContainer: 토스트 메시지 표시 영역

LoadingOverlay: 로딩 시 전체 화면 오버레이 표시

🔗 연관 문서
AuthContext.md

AppRouter.md

EmotionToastProvider.md

EmotionToastContainer.md

LoadingContext.md

LoadingOverlay.md

ThemeContext.md

✅ 완료된 기능
 앱 전체 라우팅 및 UI 설정

 글로벌 컨텍스트 설정 완료

 로딩 및 토스트 UI 삽입

📌 TODO
 에러 바운더리 도입 고려

 React Lazy 로 라우터 컴포넌트 지연 로딩 최적화 여부 검토

markdown
복사
편집

---

✅ **핵심 정리**:

- `AuthProvider` → `features/auth/context/AuthContext.md`
- `AppRouter` → `app/routes/AppRouter.md`
- `EmotionToastContainer`, `EmotionToastProvider` → `features/toast/`
- `LoadingProvider`, `LoadingOverlay`, `ThemeProvider` → `features/system/`, `features/ui/`