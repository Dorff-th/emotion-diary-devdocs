# 📄 toastHelper.ts
## 📁 위치
features/toast/utils/toastHelper.ts

---

## 🧭 역할
감정 스타일의 커스텀 토스트 메시지를 쉽게 출력할 수 있도록 도와주는 유틸리티 훅입니다.
내부적으로 useEmotionToast()를 사용하여 다양한 타입의 토스트를 한 줄 코드로 호출할 수 있게 합니다.

---

## 🔗 주요 import 목록
| 항목                | 설명              | 링크                                                     |
| ----------------- | --------------- | ------------------------------------------------------ |
| `useEmotionToast` | 감정 기반 커스텀 토스트 훅 | [`useEmotionToast.ts`](../hooks/useEmotionToast.tsx.md) |

---


## 🧩 포함 함수 구조
```text
useToastHelper()
├── showSuccess(msg)
├── showError(msg)
├── showWarning(msg)
├── showInfo(msg)
├── showGPT(msg)
└── showCustom(msg)
```
---

## 📝 설명 및 주요 로직
### ✅ useToastHelper()
내부적으로 useEmotionToast()를 호출하여 showToast()를 가져옴

다양한 토스트 타입에 맞게 메시지를 출력하는 헬퍼 함수들을 반환

type 필드는 다음 값을 가질 수 있음:

'success', 'error', 'warn', 'info', 'gpt', 'custom'

### ✅ 사용 예시

const { showSuccess, showError } = useToastHelper();

showSuccess("성공!");
showError("실패!");

---

# 📌 기타 참고
감정형 토스트 출력 방식은 UI 일관성과 UX 향상에 도움이 됨

gpt, custom 등의 추가 타입은 사용자 경험을 차별화하는 데 활용 가능

이 유틸은 실제 사용 컴포넌트에서 import만 하면 바로 사용 가능하도록 설계되어 있음

