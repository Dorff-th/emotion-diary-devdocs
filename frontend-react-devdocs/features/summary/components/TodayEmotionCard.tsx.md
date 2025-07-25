# 📄 TodayEmotionCard.tsx
## 📁 위치
features/summary/components/TodayEmotionCard.tsx

---

## 🧭 역할
오늘 회고의 감정 상태를 이모지, 한글 표현, 영어 표현으로 시각적으로 보여주는 카드 컴포넌트입니다.
사용자의 감정을 직관적으로 보여주며 Summary 화면의 상단 주요 구성요소로 사용됩니다.

---

## 🔗 주요 import 목록
항목	설명	링크
EmotionLevel	감정 점수 타입 (1~5)	emotionMap.ts
emotionEmojiMap	감정 점수 ➝ 이모지 매핑 객체	emotionMap.ts

---

## 🧩 포함 컴포넌트 트리
text
복사
편집
TodayEmotionCard
├── 이모지 (emotionEmojiMap[emotion])
├── 한글 감정 표현 (feelingKo)
└── 영어 감정 표현 (feelingEn)

---

## 📝 설명 및 주요 로직
emotion(1~5)은 EmotionLevel로 타입 제한되어 있으며, 해당 숫자에 맞는 이모지를 emotionEmojiMap에서 가져옴

feelingKo: 사용자가 입력한 감정 한마디 (한글)

feelingEn: GPT가 생성한 감정 한마디 (영어)

tsx
복사
편집
<div className="text-4xl text-center">{emotionEmojiMap[emotion]}</div>
<div className="text-center mt-2 text-lg font-semibold">{feelingKo}</div>
<div className="text-center text-sm text-gray-500">"{feelingEn}"</div>
Tailwind CSS 유틸리티 클래스를 사용해 감정 표현을 감성적으로 보여줌


## 📌 기타 참고
이 컴포넌트는 SummaryPage.tsx에서 사용되며, 오늘의 회고를 시각적으로 요약할 때 핵심적으로 활용됨

배경색은 감정을 강조하기 위해 밝은 노란색(bg-yellow-100)으로 설정되어 있음

향후 감정의 종류가 더 세분화된다면 emotionMap.ts 확장을 통해 함께 개선될 수 있음