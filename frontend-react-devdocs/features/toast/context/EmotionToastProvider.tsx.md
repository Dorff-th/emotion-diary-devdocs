# 📄 EmotionToastProvider.tsx
## 📁 위치
features/toast/context/EmotionToastProvider.tsx

---

## 🧭 역할
감정 기반 토스트 메시지 시스템의 전역 상태를 공급하는 Context Provider입니다.
내부에서 커스텀 훅 useEmotionToastState()를 통해 상태를 생성하고, 이를 하위 트리에 전달합니다.

---

## 🔗 주요 import 목록
| 항목                     | 설명                         | 링크                                                |
| ---------------------- | -------------------------- | ------------------------------------------------- |
| `ToastContext`         | 토스트 전역 상태를 공유하는 Context 객체 | [useEmotionToast.ts](../hooks/useEmotionToast.tsx.md) |
| `useEmotionToastState` | 토스트 상태와 제어 함수들을 반환하는 커스텀 훅 | [useEmotionToast.ts](../hooks/useEmotionToast.tsx.md) |
| `ReactNode`            | children 렌더링 타입            | -                                                 |


---

## 🧩 포함 컴포넌트 트리
```text
복사
편집
EmotionToastProvider
└── ToastContext.Provider
    └── value = useEmotionToastState()
        └── 상태: 메시지, 타입 등
        └── 함수: showToast(), hideToast() 등
```

## 📝 설명 및 주요 로직
EmotionToastProvider는 리액트 앱 루트 또는 특정 하위 트리에서 감정 토스트 시스템을 사용할 수 있도록 합니다.

useEmotionToastState() 훅을 통해 토스트 상태를 생성하고 ToastContext.Provider의 value로 전달.

이후 하위 컴포넌트에서는 useEmotionToast() 또는 useToastHelper() 훅을 통해 이 상태에 접근 가능.

---

## 📌 기타 참고
감정 기반 토스트란?
사용자 감정/행동에 따라 이모지, 색상, 피드백 스타일이 달라지는 동적 토스트 시스템.

사용 예: GPTFeedbackModal, DiaryInputPage, SearchResultPage 등에서 감정 기반 피드백에 활용됨.