# 📄 LoadingOverlay.tsx
## 📁 위치
features/ui/components/LoadingOverlay.tsx

---

## 🧭 역할
전역 로딩 상태가 true일 때 화면 중앙에 로딩 오버레이를 표시하는 UI 컴포넌트입니다.
귀여운 GPT 토끼 일러스트와 함께 사용자에게 로딩 중임을 시각적으로 전달합니다.

---

## 🔗 주요 import 목록
| 항목             | 설명                   | 링크                                                                          |
| -------------- | -------------------- | --------------------------------------------------------------------------- |
| `useLoading`   | 전역 로딩 상태를 가져오는 커스텀 훅 | [LoadingContext.tsx](../../../features/system/context/LoadingContext.tsx)   |
| `loadingBunny` | 로딩 애니메이션용 GPT 토끼 이미지 | [loading\_bunny\_gpt.png](../../../assets/characters/loading_bunny_gpt.png) |


---

## 🧩 포함 컴포넌트 트리
```text
복사
편집
LoadingOverlay
└── if (!isLoading) return null;
└── <div> 로딩 오버레이
    ├── <img> GPT 토끼 이미지 (animate-bounce)
    └── <div> "GPT 토끼가 준비 중이에요..." (animate-pulse)
```

## 📝 설명 및 주요 로직
useLoading() 훅을 통해 전역 상태 isLoading을 구독.

isLoading이 false인 경우 컴포넌트는 렌더링되지 않음 (return null).

로딩 중인 경우:

fixed inset-0 z-50: 전체 화면 오버레이

bg-white/80 dark:bg-black/70 backdrop-blur-sm: 배경 흐림 + 투명도 + 다크모드 대응

중앙에는 GPT 토끼 일러스트와 텍스트가 등장

애니메이션 효과:

이미지: animate-bounce

텍스트: animate-pulse

---

## 📌 기타 참고
전역 로딩 상태를 컨트롤하는 <LoadingProvider> 내부에서 동작해야 함

페이지 전환 또는 GPT 응답 대기 중 시각적 피드백을 주는 데 최적

UX 측면에서 사용자 몰입감을 높이기 위한 감성 요소로 기획된 컴포넌트