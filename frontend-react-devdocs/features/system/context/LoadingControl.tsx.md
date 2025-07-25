# 📄 LoadingControl.tsx
## 📁 위치
features/system/context/LoadingControl.tsx

---

## 🧭 역할
전역 로딩 상태를 외부에서 제어할 수 있도록 showLoading / hideLoading 메서드를 전달받고,
이를 전역에서 접근 가능한 형태로 getLoadingControl()을 통해 노출하는 전역 상태 유틸입니다.

---

## 🔗 주요 import 목록
### ❌ 외부 import 없음 (자체 정의된 타입 및 함수만 존재)

---

## 🧩 포함 구조
```text
LoadingControl.tsx
├── type LoadingControl : { showLoading, hideLoading }
├── control : 내부 상태
├── setLoadingControl(control) : 외부에서 제어 함수 설정
└── getLoadingControl() : 등록된 제어 함수 반환
```
---

## 📝 설명 및 주요 로직
### ✅ type LoadingControl
showLoading(), hideLoading() 두 가지 메서드를 가진 타입

### ✅ let control
기본은 빈 함수로 초기화된 객체 (do nothing)

### ✅ setLoadingControl(externalControl)
외부(예: LoadingProvider)에서 실제 구현된 로딩 제어 함수를 주입

이후 이 모듈을 사용하는 모든 곳에서 이 주입된 함수가 사용됨

### ✅ getLoadingControl()
현재 등록된 control 객체를 반환

axiosInstance.ts 등에서 전역 로딩을 켜고 끌 때 사용

---

## 📌 기타 참고
리액트 훅이 아닌, 전역 유틸 객체 패턴을 사용하여 어디서든 접근 가능

주로 앱 진입 시 LoadingProvider 또는 App.tsx 초기화에서 setLoadingControl이 호출될 것으로 예상됨

이 구조를 통해 API 요청 등의 사이드 이펙트가 UI 컴포넌트를 몰라도 로딩 상태를 제어 가능하게 함

