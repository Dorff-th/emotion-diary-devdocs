# 📄 EmojiDisplay.tsx
# 📁 위치
features/ui/components/EmojiDisplay.tsx

# 🧭 역할
현재 선택된 이모지를 표시하고, 다른 이모지를 선택할 수 있게 해주는 인터페이스 컴포넌트입니다.
useEmoji() 훅을 통해 전역 이모지 상태를 읽고 변경할 수 있습니다.

# 🔗 주요 import 목록  
| 항목 | 설명 | 링크 |
|------|------|------|
| `useEmoji` | 이모지 상태를 가져오고 변경하는 커스텀 훅 | [EmojiContext.tsx.md](../../system/context/EmojiContext.tsx.md) |


# 🧩 포함 컴포넌트 트리
text
복사
편집
EmojiDisplay
├── div.text-6xl (현재 선택된 이모지 표시)
└── div.flex (이모지 버튼들 나열)
    ├── button 😎
    ├── button 😭
    ├── button 😡
    └── ...

# 📝 설명 및 주요 로직
emojiList 배열을 통해 선택 가능한 이모지 리스트 구성

useEmoji()를 통해 전역 emoji 상태 및 setEmoji() 변경 함수 사용

선택된 이모지는 크게 표시 (text-6xl)

선택할 수 있는 이모지 버튼들을 나열하고 클릭 시 전역 상태 변경

현재 선택된 이모지는 강조 스타일(scale-125, opacity-100) 적용

📌 기타 참고
TailwindCSS를 활용한 반응형 애니메이션 (hover:scale-125, opacity)

감정 기반 UX의 핵심 컴포넌트로, 사용자 입력을 직관적으로 유도

상위에서 EmojiProvider로 감싼 환경에서만 동작해야 함