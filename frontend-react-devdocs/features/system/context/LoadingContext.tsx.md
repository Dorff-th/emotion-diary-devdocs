# 📄 LoadingContext.tsx
## 📁 위치
features/system/context/LoadingContext.tsx

---

## 🧭 역할
전역 로딩 상태를 관리하는 Context + Provider + Hook 조합입니다.
컴포넌트 어디서든 useLoading() 훅을 통해 로딩 상태를 제어할 수 있도록 합니다.

---

## 🔗 주요 export 목록
| 항목                    | 설명                                                        |
| --------------------- | --------------------------------------------------------- |
| `LoadingProvider`     | 전역 로딩 상태를 공급하는 Provider 컴포넌트                              |
| `useLoading`          | 로딩 상태와 제어 함수를 사용하는 커스텀 훅                                  |
| `setLoadingControl()` | 외부에서 로딩을 제어하기 위한 싱글톤 방식의 헬퍼 등록 함수 (→ `LoadingControl.ts`) |


---

## 🧩 포함 구조
```text
복사
편집
LoadingContext (Context)
├── Provider: LoadingProvider
│   ├── 상태: isLoading
│   ├── showLoading() / hideLoading()
│   └── setLoadingControl({ showLoading, hideLoading })
└── useLoading(): LoadingContextType
```
---

## 📝 설명 및 주요 로직
### 📌 LoadingProvider
내부적으로 isLoading 상태를 useState로 관리

showLoading(), hideLoading() 함수로 상태 전환

마운트 시 setLoadingControl()을 호출하여 외부에서도 로딩 제어 가능

### 📌 useLoading()
내부적으로 useContext(LoadingContext) 호출

Provider 외부에서 호출 시 에러를 던짐 (안전장치 포함)

### 📌 기타 참고
사용 예: LoadingOverlay.tsx
→ 이 컴포넌트는 isLoading === true일 때 전체 오버레이를 렌더링

외부 전역 유틸(예: API 요청 직후)에서 로딩을 제어하고자 할 경우 LoadingControl.ts를 통해 접근

