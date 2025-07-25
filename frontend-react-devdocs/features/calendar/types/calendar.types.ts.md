# 📄 calendar.types.ts
## 📁 위치
features/calendar/types/calendar.types.ts

---

## 🧭 역할
달력 렌더링 시 사용되는 날짜별 회고 및 감정 데이터의 타입을 정의합니다.
각 날짜에 대한 감정 점수, 이모지, 요약 여부 등을 포함하며, 캘린더 화면 및 관련 로직의 핵심 타입입니다.

---

## 🔗 주요 export 목록
| 타입명               | 설명                           |
| ----------------- | ---------------------------- |
| `CalendarDayData` | 날짜별 감정/회고 정보를 나타내는 타입 정의입니다. |


---

### 🧩 타입 구조
```ts
interface CalendarDayData {
  date: string;           // 날짜 (형식: YYYY-MM-DD)
  emotionScore?: number;  // 감정 점수 (선택값)
  emotionEmoji?: string;  // 감정을 나타내는 이모지 (선택값)
  hasSummary?: boolean;   // GPT 요약 여부 (선택값)
}
```
---
## 📝 설명 및 주요 필드
date: 필수 값으로, 날짜를 ISO 형식 문자열(예: "2025-07-25")로 표현합니다.

emotionScore: 해당 날짜의 감정 점수를 숫자 형태로 표현. (예: -3 ~ +3)

emotionEmoji: 감정을 직관적으로 보여줄 이모지 값. (예: 😀, 😢 등)

hasSummary: 해당 날짜의 회고에 GPT 요약이 생성되었는지 여부.

---

## 📌 기타 참고
이 타입은 useCalendarData, Calendar, CalendarDayCell 등 여러 컴포넌트에서 공유되며, 감정 기반 회고 서비스에서 핵심 역할을 합니다.

선택적 필드(?)들은 백엔드 데이터가 없거나 상태가 초기화되지 않았을 경우를 고려하여 유연하게 설계되어 있습니다.

추후 통계 기능이나 필터링 기능 확장 시에도 기반 타입으로 사용될 수 있습니다.