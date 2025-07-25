# 📄 SearchResultPage.tsx
## 📁 위치
features/search/pages/SearchResultPage.tsx

---

## 🧭 역할
회고 데이터에 대한 검색 결과 페이지를 구성합니다.
키워드, 감정 점수 범위, 날짜 범위, 검색 필드를 조합하여 조건에 맞는 회고들을 필터링하고 결과를 보여주는 기능을 담당합니다.

---

## 🔗 주요 import 목록
| 항목                                   | 설명                            | 링크                                                                               |
| ------------------------------------ | ----------------------------- | -------------------------------------------------------------------------------- |
| `useSearchParams`, `useNavigate`     | 쿼리 스트링 기반 검색 파라미터 관리 및 페이지 이동 | [react-router-dom](https://reactrouter.com/)                                     |
| `axiosInstance`                      | 검색 API 요청을 위한 Axios 인스턴스      | [axiosInstance.ts](../../../lib/axios/axiosInstance.ts)                          |
| `Header`                             | 상단 헤더 컴포넌트                    | [Header.tsx](../../../features/layout/components/Header.tsx)                     |
| `EmotionRangeSlider`                 | 감정 점수 범위를 설정하는 커스텀 슬라이더 컴포넌트  | [EmotionRangeSlider.tsx](../../../features/ui/components/EmotionRangeSlider.tsx) |
| `DatePicker`, `LocalizationProvider` | 날짜 선택 기능 및 한글화                | [@mui/x-date-pickers](https://mui.com/x/react-date-pickers/)                     |


---

## 🧩 포함 컴포넌트 트리
``` text
SearchResultPage
├── Header
├── Checkbox Group (검색 필드 선택)
├── EmotionRangeSlider
├── DatePicker (시작일 / 종료일)
├── 검색 버튼
├── 검색 결과 목록 (map entry)
└── 페이지네이션 버튼 (◀ 이전 / 다음 ▶)
```

----

## 📝 설명 및 주요 로직
### 📌 상태 관리
emotionRange: 감정 점수 범위 [min, max]

startDate, endDate: 선택된 날짜 범위

selectedFields: 검색 필드(감정 한마디, GPT 피드백 등)

query, page, size: 쿼리 파라미터 기반 검색 조건

results: 검색 결과 목록

totalPages: 전체 페이지 수

### 📌 주요 함수
fetchResults(): 현재 상태값들을 기반으로 /user/diaries/search API를 POST 호출하여 결과를 받아옴.

highlightKeyword(text, keyword): 검색어 강조(&lt;mark&gt;) 처리

handlePageChange(newPage): 페이지 변경 시 page 파라미터 갱신

toggleField(field): 검색 필드 체크박스 토글

### 📌 UI 구성
검색 조건은 카드 형태(div.p-6)로 분리

체크박스, 감정 슬라이더, 날짜 범위, 검색 버튼으로 구성

검색 결과는 리스트 형태로 출력되며, 감정 및 회고 내용은 강조 처리

페이지 하단에 페이지네이션 버튼 포함

### 📌 기타 참고
dangerouslySetInnerHTML로 highlight 처리된 HTML을 출력하므로, XSS 방지 필요 시 escape 처리 강화 고려

defaultFields: 기본 검색 필드로 ['feelingKo', 'feelingEn', 'content', 'feedback'] 사용

서버에서 emotionMap, diaryDateMap, fields, query를 받아 검색 처리

