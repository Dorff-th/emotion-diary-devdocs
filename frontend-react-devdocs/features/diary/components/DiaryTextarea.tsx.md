# 📄 DiaryTextarea.tsx
## 📁 위치
features/diary/components/DiaryTextarea.tsx

---

## 🧭 역할
사용자가 하루를 돌아보며 자유롭게 회고 내용을 작성할 수 있는 다이어리 입력 영역을 제공합니다.

---

## 🔗 주요 import 목록
| 항목 | 설명                | 링크 |
| -- | ----------------- | -- |
| 없음 | React 외 추가 의존성 없음 | -  |


---

## 🧩 포함 컴포넌트 트리
```text
DiaryTextarea
└── textarea
```

---
## 📝 설명 및 주요 로직

props:

value: 현재 회고 내용 문자열

onChange: 텍스트 변경 시 호출되는 콜백 함수

주요 UI 구성:

제목: "오늘의 회고"

텍스트 입력 영역:

textarea 컴포넌트로 구현

resize-none 설정으로 크기 조절 비활성화

다크모드 및 라이트모드 스타일 대응

UX 요소:

플레이스홀더로 작성 방향 제시: "하루를 되돌아보며 자유롭게 적어보세요..."

넉넉한 padding, rounded, shadow, transition 등으로 가독성 및 작성 경험 강화

---

## 📌 기타 참고
상위 컴포넌트에서는 useState를 통해 value를 관리하고 onChange를 통해 실시간 상태를 동기화

최소한의 기능에 집중한 단순하고 명확한 구조로, 리팩토링 시 입력 제한, 글자 수 표시 등 확장 가능

