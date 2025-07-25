# 📄 HabitChecklist.tsx
## 📁 위치
features/diary/components/HabitChecklist.tsx

---

## 🧭 역할
사용자가 오늘 완료한 습관을 체크박스로 선택할 수 있도록 돕는 UI 컴포넌트입니다. 선택된 항목은 상위 컴포넌트로 전달되어 저장 또는 분석에 활용됩니다.

---

## 🔗 주요 import 목록
| 항목 | 설명          | 링크 |
| -- | ----------- | -- |
| 없음 | 외부 모듈 의존 없음 | -  |


---

## 🧩 포함 컴포넌트 트리
```text
HabitChecklist
└── label[] (defaultHabits.map 반복)
    └── input[type="checkbox"]
```    
---
## 📝 설명 및 주요 로직
props:

selectedHabits: 현재 체크된 습관 문자열 배열

onChange: 습관 선택 변경 시 상위 컴포넌트에 새로운 배열 전달하는 콜백

동작 방식:

defaultHabits 배열을 기반으로 체크박스 목록을 렌더링

각 항목은 toggleHabit 함수를 통해 체크/해제 처리

체크 시: 배열에 추가

해제 시: 배열에서 제거

스타일:

Tailwind CSS 사용

다크모드/라이트모드 모두 대응

accent-blue-500을 통해 체크박스 색상 강조

UX 고려:

각 습관 항목은 <label> 전체 클릭으로 체크 가능

gap, rounded, shadow, border 등 UI 요소를 통해 명확한 영역 분리 및 가독성 강화

---

## 📌 기타 참고
기본 습관 목록은 defaultHabits로 하드코딩되어 있으나, 추후 props로 주입받는 방식으로 확장 가능

습관 데이터는 저장 시 habitTags로 전달되어 회고 분석이나 통계 대시보드에 활용됨

컴포넌트가 가볍고 재사용성 높아, 주간/월간 습관 확인용 UI로도 확장 가능

