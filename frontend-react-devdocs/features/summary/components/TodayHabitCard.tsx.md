# 📄 TodayHabitCard.tsx
## 📁 위치
features/summary/components/TodayHabitCard.tsx

---

## 🧭 역할
오늘 사용자가 체크한 습관 목록을 이모지와 함께 보여주는 카드 컴포넌트입니다.
습관이 없을 경우 대체 메시지를 출력하며, SummaryPage 내 요약 정보 중 하나로 사용됩니다.

## 🔗 주요 import 목록
| 항목              | 설명                         | 링크        |
| --------------- | -------------------------- | --------- |
| `habits`        | 문자열 배열 형태의 습관 목록 (`Props`) | 전달 props  |
| `habitEmojiMap` | 습관 이름 ➝ 이모지 매핑 객체          | (파일 내 정의) |


---

## 🧩 포함 컴포넌트 트리

TodayHabitCard
├── 습관이 없으면 → "오늘은 기록된 습관이 없어요 😶"
└── 습관이 있으면 → 태그 스타일 습관 목록 렌더링
    ├── 🧘 명상
    ├── 📚 독서
    └── ...




## 📝 설명 및 주요 로직
habits는 문자열 배열이며, 체크된 습관들이 전달됨 (예: ['명상', '운동'])

습관마다 이모지를 매핑하기 위해 habitEmojiMap 객체를 사용

습관이 없으면 텍스트 "오늘은 기록된 습관이 없어요 😶" 출력

습관이 있으면 .map()을 통해 각 항목을 태그 형태로 렌더링

---

tsx
복사
편집
<span className="bg-white px-3 py-1 rounded-full ...">
  {habitEmojiMap[habit] || '🔸'} {habit}
</span>
Tailwind CSS의 rounded-full, shadow-sm, border 등을 활용한 스타일링 적용

##📌 기타 참고
habitEmojiMap은 파일 내부에서 하드코딩된 객체이며, 새로운 습관을 추가할 경우 여기에 확장 필요

SummaryPage.tsx에서 parsedHabits로 전달받은 배열이 이 컴포넌트의 props.habits로 전달됨

다국어 또는 사용자 정의 습관 기능이 추가될 경우, 이모지 매핑 방식의 확장이 필요할 수 있음

