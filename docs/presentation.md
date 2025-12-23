---
marp: true
theme: gaia
paginate: true
backgroundColor: #fff
style: |
  section {
    font-family: 'Malgun Gothic', 'Apple SD Gothic Neo', sans-serif;
  }
  h1 {
    color: #2c3e50;
  }
  h2 {
    color: #34495e;
  }
---

# Mobile User Behavior Analytics Platform

**모바일 앱 사용자 행동 데이터 기반 지표 & 실험 분석**

토스뱅크 데이터 분석가 포트폴리오 프로젝트

---

## 📌 프로젝트 개요

**목표**: 모바일 앱 사용자 행동 데이터를 분석하여 핵심 지표를 정의하고, A/B 테스트를 통한 가설 검증 및 비즈니스 인사이트 도출

**핵심 가치**:
- 📊 데이터 기반 의사결정
- 🧪 실험을 통한 가설 검증
- 📈 비즈니스 임팩트 정량화

---

## 🎯 해결하고자 하는 문제

### 1. 데이터 기반 의사결정 부재
직관에 의존한 의사결정 → 데이터 기반 의사결정

### 2. 핵심 지표 부재
성과 측정 불가 → Retention, LTV, Funnel 등 핵심 지표 정의

### 3. 실험 검증 미흡
효과 검증 불가 → A/B 테스트로 정량적 검증

### 4. 인사이트 전달 어려움
분석 결과 전달 실패 → 스토리텔링 기반 커뮤니케이션

---

## 📊 핵심 기능 (MVP Scope)

### 1. 데이터 수집 및 전처리
- SQL 기반 데이터 추출 및 정제
- 사용자 행동 로그, 세션 데이터 수집
- 파생 변수 생성

### 2. 핵심 지표 계산
- **Retention Rate**: Day 1/7/30 재방문율
- **Cohort Analysis**: 코호트별 행동 패턴
- **Conversion Funnel**: 단계별 전환율
- **LTV**: 사용자 생애 가치

---

## 📊 핵심 기능 (계속)

### 3. A/B 테스트 설계 및 분석
- 실험 설계 (가설, 대조군/실험군)
- 통계 검정 (t-test, Chi-square)
- 효과 크기 및 신뢰구간 계산

### 4. 데이터 시각화 및 대시보드
- Tableau / Power BI 대시보드
- Python 시각화 (Matplotlib, Seaborn)
- 인터랙티브 차트 및 리포트

---

## 🛠️ 기술 스택

### 데이터 처리
- **SQL**: PostgreSQL (데이터 추출 및 정제)
- **Python**: Pandas, NumPy (분석)
- **Jupyter Notebook**: EDA

### 통계 분석
- **Python**: SciPy, StatsModels
- **A/B Testing**: t-test, Chi-square

### 시각화
- **Tableau / Power BI**: 대시보드
- **Python**: Matplotlib, Seaborn, Plotly

---

## 📈 핵심 지표 상세

### Retention Rate (재방문율)
```
Day 1 Retention = (재방문 사용자 / 신규 가입자) × 100
```
- Day 1: 가입 다음날 재방문율
- Day 7: 가입 7일 후 재방문율
- Day 30: 가입 30일 후 재방문율

### Cohort Analysis
가입 시기별 사용자 그룹의 행동 패턴 비교

### Conversion Funnel
```
회원가입 → 프로필 작성 → 첫 거래 → 재거래
```

---

## 🧪 A/B 테스트 시나리오

### 시나리오 1: 푸시 알림 최적화
- **가설**: 개인화된 푸시가 재방문율 향상
- **측정 지표**: Day 1/7 Retention
- **통계 검정**: t-test

### 시나리오 2: 온보딩 플로우 개선
- **가설**: 간소화된 온보딩이 전환율 향상
- **측정 지표**: 온보딩 완료율, 첫 거래 전환율
- **통계 검정**: Chi-square test

### 시나리오 3: 할인 이벤트 효과
- **가설**: 10% 할인이 LTV 증가
- **측정 지표**: 30일 LTV, 재구매율
- **통계 검정**: t-test

---

## 📊 데이터 흐름

```
1. 모바일 앱 이벤트 로그 수집
   ↓
2. PostgreSQL 데이터베이스 저장
   ↓
3. SQL 기반 데이터 추출
   ↓
4. Python 분석
   - 핵심 지표 계산
   - A/B 테스트 통계 검정
   ↓
5. 시각화 및 리포트
   - Tableau 대시보드
   - Python 차트
```

---

## 🗓️ 개발 로드맵

### Phase 1: 데이터 인프라 구축 (Week 1-2)
- PostgreSQL 데이터베이스 설계
- 가상 사용자 데이터 생성 (1만명+)
- SQL 쿼리 작성

### Phase 2: 핵심 지표 계산 (Week 3-4)
- Retention, Cohort, Funnel, LTV 계산
- 세그먼트별 비교 분석

---

## 🗓️ 개발 로드맵 (계속)

### Phase 3: A/B 테스트 프레임워크 (Week 5-6)
- 실험 설계 프레임워크 구축
- 3가지 시나리오 A/B 테스트 수행
- 통계 검정 및 결과 분석

### Phase 4: 시각화 및 대시보드 (Week 7-8)
- Tableau/Power BI 대시보드 구축
- Python 시각화
- 분석 리포트 및 슬라이드 작성

---

## 📈 예상 결과 (예시)

### Retention Analysis
- Day 1 Retention: 45%
- Day 7 Retention: 28%
- Day 30 Retention: 15%

### Cohort Insights
- 2024년 1월 코호트가 가장 높은 Retention (32%)
- iOS 사용자가 Android 대비 20% 높은 Retention

### A/B Test Results
- 푸시 알림 최적화: Day 1 Retention **8% 증가** (p < 0.01)
- 온보딩 개선: 첫 거래 전환율 **15% 증가** (p < 0.05)
- 할인 이벤트: 30일 LTV **12% 증가** (p < 0.05)

---

## 🎓 토스뱅크 요구사항 매핑

| 요구사항 | 프로젝트 반영 |
|---------|-------------|
| SQL 데이터 추출·정제 | PostgreSQL 쿼리 작성 ✅ |
| 모바일 서비스 지표 | Retention, LTV, Cohort, Funnel ✅ |
| A/B 테스트 설계·검증 | 3가지 시나리오 실험 ✅ |
| 데이터 시각화 툴 | Tableau/Power BI 대시보드 ✅ |
| 비즈니스 커뮤니케이션 | 스토리텔링 리포트 ✅ |
| Python 통계분석 | SciPy, StatsModels ✅ |

---

## 💡 프로젝트 차별화 포인트

✅ **실무 중심**: 토스뱅크 실제 업무와 유사한 분석 프로세스
✅ **통합 역량**: SQL + Python + 시각화 툴 통합 활용
✅ **통계적 엄밀성**: A/B 테스트 통계 검정 및 검증
✅ **비즈니스 임팩트**: 정량화된 결과 및 액션 아이템
✅ **재현 가능성**: 모든 분석 코드 및 쿼리 문서화
✅ **포트폴리오 품질**: GitHub, 대시보드, 리포트 완비

---

## 📚 포트폴리오 구성

### GitHub Repository
- README, PRD, TASKS 문서
- SQL 쿼리 모음
- Jupyter Notebooks (4개)
- Python 스크립트

### 대시보드
- Tableau/Power BI 대시보드 (3개)
- 스크린샷 및 링크

### 분석 리포트
- 슬라이드 (PPT): 문제 → 분석 → 인사이트 → 액션
- 문서: 상세 분석 결과

---

## 🎯 기대 효과

### 실무 역량 증명
- 토스뱅크 데이터 분석가 필수 역량 100% 시연
- 실제 업무와 유사한 분석 프로세스 경험

### 포트폴리오 차별화
- 단순 튜토리얼이 아닌 실전 프로젝트
- 비즈니스 임팩트 중심의 분석

### 취업 경쟁력
- 면접 시 구체적인 경험 설명 가능
- 실무 즉시 투입 가능한 역량 증명

---

## 📚 참고 자료

- **GitHub Repository**: [UpstageDemo](https://github.com/ts6nqswnr8-sudo/UpstageDemo)
- **Documentation**: PRD, TASKS, README
- **Issues**: 7개 Phase별 작업 이슈

---

## 🙏 Thank You!

**Questions?**

GitHub: [ts6nqswnr8-sudo/UpstageDemo](https://github.com/ts6nqswnr8-sudo/UpstageDemo)

**Built for Toss Bank Data Analyst Portfolio**
