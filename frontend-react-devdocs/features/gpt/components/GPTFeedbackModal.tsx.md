# 📄 GPTFeedbackModal.tsx
## 📁 위치
features/gpt/components/GPTFeedbackModal.tsx
---

## 🧭 역할
GPT가 생성한 피드백 메시지를 사용자에게 시각적으로 보여주는 모달 컴포넌트입니다. 자동으로 사라지거나 수동으로 닫을 수 있습니다.

---

## 🔗 주요 import 목록
| 항목                                 | 설명                          | 링크                                                      |
| ---------------------------------- | --------------------------- | ------------------------------------------------------- |
| `feedbackStyleMap`, `FeedbackType` | 피드백 타입별 스타일(이모지, 배경색 등)을 제공 | [feedbackTypes.ts](../../gpt/types/feedbackTypes.ts.md) |


---

## 🧩 포함 컴포넌트 트리
```text
GPTFeedbackModal
└── div.modalBackdrop
    └── div.modalBox
        ├── 저장 중... 텍스트
        ├── 이모지 + 메시지
        └── OK 버튼
```

## 📝 설명 및 주요 로직
props:

message: GPT가 생성한 피드백 문자열

onClose: 모달 닫기 콜백 함수

type (optional): 피드백 스타일 타입 ('encourage', 'scold', 'roast', 'random', 'default')

duration (optional): 모달이 자동으로 닫히는 시간 (기본값: 3000ms)

동작 방식:

useEffect를 사용하여 duration 시간이 지나면 onClose() 자동 호출

스타일은 feedbackStyleMap에서 type에 따라 동적으로 설정

배경색, 테두리색, 이모지, 라벨 등 피드백 성격에 맞춤 표현

시각 효과:

backdrop-blur-sm, animate-slideDownCenter 등의 클래스를 통해 모달 진입 시 부드러운 애니메이션

반투명 검은 배경 + 중앙 정렬 + 그림자 효과

버튼:

"OK" 버튼 클릭 시 수동으로도 모달을 닫을 수 있음

---

## 📌 기타 참고
이 모달은 회고 저장 시 또는 GPT 응답 시점에 사용자에게 피드백을 직관적으로 보여주기 위해 사용됨

UX 측면에서 피드백에 이모지를 활용하여 감정 전달력 강화

duration과 onClose는 상위에서 제어할 수 있어 유연한 사용 가능

