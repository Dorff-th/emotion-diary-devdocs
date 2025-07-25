# 📄 GptFeelingLoadingModal.tsx
## 📁 위치
features/ui/components/GptFeelingLoadingModal.tsx

---

## 🧭 역할
사용자가 GPT 영어 표현 추천을 요청한 후 응답을 기다리는 동안 보여주는 감성적인 로딩 모달입니다. 시각적 아이콘과 문구로 기다리는 시간을 부드럽게 안내합니다.

## 🔗 주요 import 목록
| 항목         | 설명                                 | 링크                                                      |
| ---------- | ---------------------------------- | ------------------------------------------------------- |
| `Dialog`   | 접근성 좋은 모달 UI 제공 (Headless UI 구성요소) | [Headless UI Docs](https://headlessui.com/react/dialog) |
| `Sparkles` | 반짝이는 아이콘 (로딩 표현용)                  | [lucide-react](https://lucide.dev/icons/sparkles)       |


---

## 🧩 포함 컴포넌트 트리
```text
GptFeelingLoadingModal
└── Dialog
    └── div.modalBox
        ├── Sparkles 아이콘
        ├── 메시지 헤더 (GPT가 정리 중...)
        └── 서브 메시지 (감정에 맞는 표현 고민 중...)
```
        
## 📝 설명 및 주요 로직
props:

isOpen: 모달의 열림 여부 (true일 때만 렌더링됨)

동작 방식:

isOpen이 false이면 null 반환 → 모달 미표시

열려 있는 경우 Dialog를 통해 전체 화면에 반투명 배경과 함께 중앙 정렬된 모달 표시

닫기 기능은 내부적으로 비활성화되어 있음 (onClose={() => {}} → 강제 닫기 방지)

시각적 요소:

Sparkles 아이콘에 animate-spin-slow 적용으로 부드러운 회전

감성적인 문구:

“GPT가 당신의 기분을 말로 정리 중이에요...”

“감정에 딱 맞는 영어 표현을 고민하고 있어요 💭”

디자인:

Tailwind 기반 다크모드 지원 (bg-white / dark:bg-gray-800, text-gray-600 등)

animate-pulse로 전체 박스에 미세한 생동감 부여

---

## 📌 기타 참고
사용자에게 로딩 중임을 단순히 “로딩...”이 아닌, 감성적 언어로 표현해 사용 경험을 부드럽게 만듦

Headless UI의 Dialog를 활용함으로써 접근성(스크린 리더 등) 고려

GPTFeedbackModal과는 다르게 실제 GPT 응답 결과가 아닌 기다림에 초점을 맞춘 전용 UI