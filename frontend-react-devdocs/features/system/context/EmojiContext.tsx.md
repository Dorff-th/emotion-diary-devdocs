# 📄 EmojiContext.tsx
# 📁 위치
features/system/context/EmojiContext.tsx

# 🧭 역할
전역 이모지 상태를 관리하는 React Context입니다.
사용자가 선택한 이모지를 로컬스토리지에 저장하고, 앱 전역에서 접근할 수 있도록 제공합니다.

# 🔗 주요 import 목록
항목	설명	링크
createContext, useContext	React의 Context API 사용을 위한 훅 및 생성자	-
useState, useEffect	상태 및 사이드 이펙트 처리 훅	-
EmojiProvider	전역 이모지 상태를 공급하는 Context Provider	(현재 파일 내 정의)
useEmoji	이모지 컨텍스트를 쉽게 사용할 수 있도록 하는 커스텀 훅	(현재 파일 내 정의)

# 🧩 포함 컴포넌트 트리 (Provider 기준)
text
복사
편집
EmojiProvider
└── children (하위 컴포넌트에서 useEmoji()로 context 접근 가능)

# 📝 설명 및 주요 로직
EmojiContext를 생성하여 전역 상태 공유

EmojiProvider는 children을 감싸고 emoji, setEmoji 상태를 공급

초기 emoji 값은 localStorage에서 불러옴 (기본: 😎)

emoji가 바뀔 때마다 localStorage에 자동 저장됨 (useEffect)

useEmoji()는 context를 쉽게 사용하게 해주는 커스텀 훅

# 📌 기타 참고
로그인 페이지나 사용자 인터페이스에서 감정 표현 등 다양한 곳에 활용 가능

emoji 상태는 이 앱의 UX에서 감정 기반 UI 요소를 구현하는 핵심 요소

