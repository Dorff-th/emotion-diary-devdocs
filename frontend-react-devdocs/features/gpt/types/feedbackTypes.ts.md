# 📄 feedbackTypes.ts
## 📁 위치
features/gpt/types/feedbackTypes.ts

---

## 🧭 역할
GPT 피드백 스타일을 정의하는 타입, 인터페이스, 매핑 객체를 포함하여 다양한 피드백 유형을 코드 전반에서 일관되게 사용할 수 있도록 정의합니다.

---

## 🔗 주요 export 목록
항목	설명
FeedbackType	피드백 타입을 문자열 리터럴 유니언으로 정의 ('encourage', 'scold' 등)
FeedbackStyle	각 피드백 스타일의 이모지, 색상, 라벨 정보를 포함한 타입
feedbackStyleMap	FeedbackType과 시각적 스타일을 연결하는 매핑 객체

---

## 🧩 구조
```ts
export type FeedbackType =
  | 'encourage'
  | 'scold'
  | 'roast'
  | 'random'
  | 'default';
```
```ts
export interface FeedbackStyle {
  emoji: string;
  bgColor: string;
  borderColor: string;
  label: string;
}
```
```ts
export const feedbackStyleMap: Record<FeedbackType, FeedbackStyle> = {
  encourage: { ... },
  scold: { ... },
  ...
};
```
## 📝 설명 및 주요 포인트
FeedbackType:

피드백의 유형을 문자열 리터럴로 제한하여 코드 자동완성 및 타입 안정성을 확보

사용 가능한 타입: 'encourage'(격려), 'scold'(갈굼), 'roast'(혼냄), 'random', 'default'

FeedbackStyle:

UI에서 피드백 스타일을 표현하기 위한 시각적 속성을 지정

emoji: 감정 표현용 이모지

bgColor, borderColor: Tailwind CSS 기반 색상 클래스

label: 사용자에게 보여질 한글 라벨

feedbackStyleMap:

FeedbackType에 따라 각 스타일을 연결하는 맵

예: 'scold' → 🔥, 붉은 배경과 테두리, 라벨은 "갈굼"

드롭다운, 피드백 카드, 버튼 등 다양한 UI에서 공통으로 사용

---

## 📌 기타 참고
이 구조는 새로운 피드백 타입을 추가하거나 제거할 때도 변경 포인트가 최소화되어 유지보수가 쉽습니다.

FeedbackTypeSelect.tsx 등에서는 이 맵을 기반으로 드롭다운을 자동 생성합니다.

default 타입은 fallback 용도로 활용되며, 실제 사용자에게는 노출되지 않을 수도 있습니다.