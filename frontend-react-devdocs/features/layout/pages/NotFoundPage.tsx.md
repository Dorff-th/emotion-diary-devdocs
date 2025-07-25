# 📄 NotFoundPage.tsx
## 📁 위치
features/layout/pages/NotFoundPage.tsx

---

## 🧭 역할
유효하지 않은 경로(URL) 접근 시 렌더링되는 404 에러 페이지입니다.
사용자가 잘못된 경로로 이동했을 때 안내 메시지를 띄우고 홈으로 돌아갈 수 있는 링크를 제공합니다.

---

## 🔗 주요 import 목록
| 항목               | 설명                    | 링크                                                             |
| ---------------- | --------------------- | -------------------------------------------------------------- |
| `Link`           | 홈으로 돌아가기 위한 내부 라우팅 링크 | [react-router-dom](https://reactrouter.com/)                   |
| `useToastHelper` | 커스텀 토스트 메시지 출력 훅      | [toastHelper.ts](../../../features/toast/utils/toastHelper.ts) |


---

## 🧩 포함 컴포넌트 트리
```text
NotFoundPage
├── useEffect() → showCustom('존재하지 않는 페이지예요 🥲')
└── <div> 404 UI 구성
    ├── 🐰 404 아이콘
    ├── 안내 메시지
    └── Link → "/"
```
---

## 📝 설명 및 주요 로직
컴포넌트가 마운트되면 useEffect()를 통해 토스트 메시지 출력:

"존재하지 않는 페이지예요 🥲"

UI는 중앙 정렬된 화면으로 구성되며, 404 이모지와 함께 안내 메시지 표시

하단에 "홈으로 돌아가기" 버튼이 있어 / 경로로 이동 가능

---

## 📌 기타 참고
dark mode를 고려한 배경 및 텍스트 색상 적용 (bg-white, dark:bg-gray-900, text-gray-800, dark:text-white)

전역적으로 라우팅이 설정된 <Routes>에서 fallback으로 연결됨 (path="*")