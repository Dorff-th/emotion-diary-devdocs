# 📄 EmotionBarChart.tsx
## 📁 위치
features/statistics/components/EmotionBarChart.tsx

---

## 🧭 역할
감정 점수별 빈도를 막대 차트(BarChart)로 시각화하여, 특정 감정 점수가 얼마나 자주 나타났는지를 한눈에 보여주는 컴포넌트입니다.
---

## 🔗 주요 import 목록
| 항목                                             | 설명                                                          | 링크                                           |
| ---------------------------------------------- | ----------------------------------------------------------- | -------------------------------------------- |
| `BarChart`, `Bar`, `XAxis`, `YAxis`, `Tooltip` | [Recharts](https://recharts.org/en-US/) 라이브러리의 주요 차트 구성 요소들 | [recharts 공식문서](https://recharts.org/en-US/) |
| `React`                                        | React 기본 import                                             | -                                            |


---

## 🧩 포함 컴포넌트 트리
```text
EmotionBarChart
└── BarChart
    ├── XAxis (score)
    ├── YAxis (count)
    ├── Tooltip
    └── Bar (dataKey="count")
```
---

## 📝 설명 및 주요 로직
props.frequency는 감정 점수를 키(number), 빈도수를 값(number)으로 가지는 객체입니다.

이를 Object.entries()로 변환하여 [{ score, count }] 형태의 배열로 가공.

score는 X축, count는 Y축으로 설정하여 막대 차트를 구성합니다.

Tooltip을 포함하여 각 바에 마우스 오버 시 값이 표시됩니다.

전체 폭과 높이는 각각 350x200으로 고정되어 있으며, 추후 반응형 개선 여지가 있습니다.

## 📌 기타 참고
score는 문자열로 변환된 상태로 XAxis에 전달되며, 정렬이 필요하면 추가 가공 필요.

recharts 기반이기 때문에 테마/스타일 커스터마이징 가능성이 높습니다.

상위 컴포넌트인 EmotionStatsPage.tsx에서 사용됩니다.

다음 컴포넌트도 이어서 요청해 주세요. 동일한 형식으로 계속 정리해드릴게요.