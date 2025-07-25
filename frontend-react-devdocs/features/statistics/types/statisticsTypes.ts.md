# 📄 statisticsTypes.ts
## 📁 위치
features/statistics/types/statisticsTypes.ts

---

## 🧭 역할
감정 통계 기능에 사용되는 타입 정의 파일로, 기간 선택 옵션(PeriodOption)에 대한 명확한 타입 제약을 제공합니다.

---

## 🔗 주요 export 목록
| 항목             | 설명                                             |              |               |                           |
| -------------- | ---------------------------------------------- | ------------ | ------------- | ------------------------- |
| `PeriodOption` | 감정 통계를 조회할 때 사용할 기간 필터 옵션 타입 정의. \`'this-week' | 'this-month' | 'last-7-days' | 'custom'\` 네 가지 값을 허용합니다. |


---

## 🧩 타입 구조
```ts
export type PeriodOption =
  | 'this-week'     // 이번 주
  | 'this-month'    // 이번 달
  | 'last-7-days'   // 최근 7일
  | 'custom';       // 사용자 지정
```

## 📝 설명 및 주요 용도
PeriodOption은 통계 조회 시 선택 가능한 기간 필터 타입입니다.

문자열 리터럴 유니언 타입으로 정의되어 있어, 유효하지 않은 문자열 사용을 방지할 수 있습니다.

주요 사용 위치는 날짜 유틸리티 함수 getDateRange 및 통계 페이지 EmotionStatsPage입니다.

---

## 📌 기타 참고
TypeScript의 리터럴 타입을 활용하여 정해진 값만 허용되도록 제한함으로써 안전한 코드 작성을 유도합니다.

UI의 기간 선택 드롭다운 옵션과 정확히 매칭되어야 하며, i18n 또는 레이블 매핑이 필요한 경우 별도 객체 또는 enum으로 분리해도 좋습니다.