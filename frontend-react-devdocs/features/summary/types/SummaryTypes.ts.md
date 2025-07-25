# 📄 SummaryTypes.ts
## 📁 위치
features/summary/types/SummaryTypes.ts

---

## 🧭 역할
회고 요약 화면 및 API에서 사용하는 데이터 구조를 정의한 타입스크립트 인터페이스 파일입니다.
SummaryData 인터페이스는 오늘의 감정 회고 데이터 전체를 표현하는 기본 단위로 사용됩니다.

---

## 🔗 주요 import 목록
외부 import는 없습니다.

---

## 🧩 포함 타입 구조
ts
복사
편집
export interface SummaryData {
  diaryDate: string;
  emotion: number;
  feelingKo: string;
  feelingEn: string;
  habitTags: string;
  content: string;
  summary?: string;
  feedback?: string;
}

---

## 📝 필드 설명
필드명	타입	설명
diaryDate	string	회고 작성 날짜 (YYYY-MM-DD 형식)
emotion	number	감정 점수 (1 ~ 5 범위)
feelingKo	string	사용자가 입력한 감정 한마디 (한글)
feelingEn	string	GPT가 생성한 감정 한마디 (영어)
habitTags	string	체크된 습관 목록 (JSON 문자열)
content	string	사용자가 입력한 회고 내용 전체
summary	string (optional)	GPT가 생성한 회고 요약
feedback	string (optional)	GPT가 생성한 격려 또는 피드백

---

## 📌 기타 참고
habitTags는 문자열이지만 실제 사용 시에는 JSON.parse(habitTags) 형태로 배열로 변환하여 사용됩니다.

summary, feedback 필드는 옵셔널이기 때문에 GPT 요약 생성 전에는 존재하지 않을 수 있습니다.

이 타입은 useSummaryData, summaryApi, SummaryCard, FeedbackCard, TodayEmotionCard 등 다양한 컴포넌트에서 공통적으로 활용됩니다.