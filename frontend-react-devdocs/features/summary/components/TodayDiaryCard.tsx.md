# 📄 TodayDiaryCard.tsx.tsx
## 📁 위치
features/summary/components/TodayDiaryCard.tsx.tsx

---

# 🧭 역할

사용자가 입력한 오늘의 회고 내용을 보여주는 카드 컴포넌트입니다.
오늘의 회고 내용이 없을 경우 대체 문구를 보여줍니다.

---

# 🔗 주요 import 목록
| 항목                  | 설명          |
| ------------------- | -------------------|
| `content`    |  오늘의 회고 내용 문자열    | 



---

# 🧩 포함 컴포넌트 트리
```text
FeedbackCard
├── GPT 피드백 텍스트
└── (피드백이 없을 경우) 안내 문구
    └── (주석 처리된) "피드백 생성" 버튼
```
---

# 📝 설명 및 주요 로직
Props:

content?: 전달된 오늘의 회고 문자열



내부 상태:


오늘의 회고가 있을 경우:

```tsx
<p className="text-sm text-gray-700 whitespace-pre-wrap">{content}</p>
```

오늘의 회고가 없을 경우:

```tsx
<p className="text-sm text-gray-500 mb-2">회고를 작성하지 않았어요.</p>
```
---

# 📌 기타 참고
이 컴포넌트는 SummaryPage.tsx 내 TodayDiaryCard 영역에서 사용됨



