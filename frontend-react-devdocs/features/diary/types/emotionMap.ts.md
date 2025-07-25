# 📄 emotionMap.ts
## 📁 위치
features/diary/types/emotionMap.ts

---

## 🧭 역할
회고 작성 및 요약 화면 등에서 감정 상태를 표현하기 위해 사용하는 이모지/라벨 정보를 정의한 타입 및 상수 모음입니다.
감정 점수(EmotionLevel)에 따라 이모지와 라벨을 매핑하고, 관련 정보를 쉽게 참조할 수 있도록 맵 형태로 제공합니다.

---

## 🔗 주요 export 목록
항목	설명
EmotionLevel	감정 점수 타입 (1~5)
EmotionItem	감정 리스트 항목 구조 정의
emotionList	감정 점수별 이모지/라벨 목록
emotionEmojiMap	감정 점수 ➝ 이모지 매핑 객체
emotionLabelMap	감정 점수 ➝ 라벨 매핑 객체

---

## 🧩 포함 구조
```ts
EmotionLevel          // 1 | 2 | 3 | 4 | 5
EmotionItem           // { value, emoji, label }
emotionList           // EmotionItem[]
emotionEmojiMap       // Record<EmotionLevel, string>
emotionLabelMap       // Record<EmotionLevel, string>
```

---

## 📝 설명 및 주요 로직
1. EmotionLevel
ts
복사
편집
export type EmotionLevel = 1 | 2 | 3 | 4 | 5;
감정 점수는 1~5까지의 숫자로 고정

이 타입은 DiaryEntry, TodayEmotionCard 등에서 emotion 필드 타입으로 사용됨

2. emotionList
```ts
[
  { value: 1, emoji: '😢', label: '슬픔' },
  { value: 2, emoji: '😐', label: '무덤덤' },
  { value: 3, emoji: '🙂', label: '보통' },
  { value: 4, emoji: '😄', label: '좋음' },
  { value: 5, emoji: '🤩', label: '최고' },
]
```
감정 점수와 매칭되는 emoji, label을 배열 형태로 정의

3. emotionEmojiMap, emotionLabelMap
```ts
export const emotionEmojiMap: Record<EmotionLevel, string> = ...
export const emotionLabelMap: Record<EmotionLevel, string> = ...
emotionList를 기반으로 reduce를 활용해 객체 형태로 변환
```

예시:

```ts
emotionEmojiMap[4] => '😄'
emotionLabelMap[1] => '슬픔'
```

---

## 📌 기타 참고
이 데이터는 사용자 회고를 시각화할 때 직관적인 UX 제공에 활용됨

TodayEmotionCard, DiaryInputPage, SummaryPage 등에서 사용됨

추후 다국어 지원 시 label 필드는 별도로 처리될 수 있음