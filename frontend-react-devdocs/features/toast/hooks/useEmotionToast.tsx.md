# 📄 useEmotionToast.ts
## 📁 위치
features/toast/hooks/useEmotionToast.ts

---

## 🧭 역할
감정 기반의 커스텀 토스트 메시지를 상태로 관리하고 전역에서 사용할 수 있게 해주는 커스텀 훅과 Context를 제공합니다.
showToast, removeToast 등을 통해 다양한 타입의 알림을 표시할 수 있습니다.

🔗 주요 import 목록
| 항목                                        | 설명                          | 링크 |
| ----------------------------------------- | --------------------------- | -- |
| `createContext`, `useContext`, `useState` | React 기본 훅 및 Context API 사용 | -  |

---


## 🧩 포함 구조
```text
useEmotionToast.ts
├── ToastType (유형 정의: success, error, info, warn, gpt, custom)
├── EmotionToast (토스트 객체 구조)
├── EmotionToastState (상태 인터페이스)
├── ToastContext
├── useEmotionToastState() : 상태 생성 훅
└── useEmotionToast() : Context 접근 훅
```

---

## 📝 설명 및 주요 로직
### ✅ 타입 정의
ToastType: 토스트의 종류 ('success' | 'error' | 'info' | 'warn' | 'gpt' | 'custom')

EmotionToast: 개별 토스트 메시지 구조 (id, message, type)

EmotionToastInput: type은 선택형으로 기본값은 'info'

### ✅ useEmotionToastState()
useState로 toasts 배열 관리

showToast() → 새로운 toast 추가, 3초 후 자동 제거

removeToast(id) → 특정 toast 수동 제거

### ✅ useEmotionToast()
ToastContext를 통해 전역 toast 상태를 사용하는 훅

ToastContext.Provider로 감싸지 않으면 에러 발생 (EmotionToastProvider 필요)

---

## 📌 기타 참고
이 훅과 상태는 별도의 Provider(EmotionToastProvider)에서 공급되어야 정상 동작

toastHelper.ts에서 이 훅을 활용하여 다양한 단축 토스트 함수를 제공

id는 Date.now().toString()으로 생성되어 중복 가능성 낮음