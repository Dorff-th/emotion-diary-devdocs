# 📄 LoginPage.tsx
## 📁 위치
features/auth/pages/LoginPage.tsx

---

## 🧭 역할
로그인 화면을 구성하는 페이지 컴포넌트입니다.
감정 입력 및 로그인 기능을 유도하는 시각적으로 매력적인 UI를 제공합니다.
EmojiProvider를 통해 이모지 컨텍스트를 공급하며, LoginForm, EmojiDisplay, FooterMessage, ThemeToggle 등 다양한 UI 컴포넌트를 포함합니다.

---

## 🔗 주요 import 목록
| 항목              | 설명                         | 링크                                                               |
| --------------- | -------------------------- | ---------------------------------------------------------------- |
| `EmojiProvider` | 이모지 컨텍스트를 전역에서 사용할 수 있게 제공 | [EmojiContext.tsx.md](../../system/context/EmojiContext.tsx.md)  |
| `EmojiDisplay`  | 상단에 이모지를 보여주는 컴포넌트         | [EmojiDisplay.tsx.md](../../ui/components/EmojiDisplay.tsx.md)   |
| `LoginForm`     | 로그인 입력 폼 UI                | [LoginForm.tsx.md](../components/LoginForm.tsx.md)               |
| `FooterMessage` | 로그인 화면 하단 안내 메시지           | [FooterMessage.tsx.md](../../ui/components/FooterMessage.tsx.md) |
| `ThemeToggle`   | 다크모드/라이트모드 토글 버튼           | [ThemeToggle.tsx.md](../../ui/components/ThemeToggle.tsx.md)     |


---

# 🧩 포함 컴포넌트 트리
```text
LoginPage
├── EmojiProvider
    └── div.card (배경 + 로그인박스)
        ├── ThemeToggle
        ├── EmojiDisplay
        ├── h2 (오늘 하루 어땠나요?)
        ├── LoginForm
        └── FooterMessage
```
---

## 📝 설명 및 주요 로직
EmojiProvider로 감정 이모지 컨텍스트를 하위 컴포넌트에 전달

전체 화면은 그라디언트 배경 및 다크모드 대응

ThemeToggle로 테마 전환 가능

EmojiDisplay로 상단 이모지 표시

LoginForm을 통해 사용자 로그인 입력 처리

FooterMessage로 하단 메시지 표시

---

# 📌 기타 참고
반응형 UI (max-w-sm)와 함께 TailwindCSS로 정교하게 스타일링됨

다크모드와 라이트모드 전환 애니메이션 (transition-colors) 포함

로그인 페이지이지만 감정 기반 UI 요소(EmojiDisplay, 오늘 하루 어땠나요?)를 통해 사용자 친화적인 접근 유도