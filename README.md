# Mobile User Behavior Analytics Platform

[![GitHub Issues](https://img.shields.io/github/issues/ts6nqswnr8-sudo/UpstageDemo)](https://github.com/ts6nqswnr8-sudo/UpstageDemo/issues)
[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![SQL](https://img.shields.io/badge/SQL-PostgreSQL-336791.svg)](https://www.postgresql.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> 모바일 앱 사용자 행동 데이터 기반 지표 분석 및 A/B 테스트 플랫폼

## 📖 프로젝트 개요

**Mobile User Behavior Analytics Platform**은 모바일 서비스의 사용자 행동 데이터를 분석하여 핵심 지표를 계산하고, A/B 테스트를 통한 가설 검증 및 비즈니스 인사이트를 도출하는 데이터 분석 플랫폼입니다.

토스뱅크 데이터 분석가 포지션 요구사항을 100% 반영한 포트폴리오 프로젝트입니다.

### 주요 특징

- 📊 **핵심 지표 분석**: Retention, Cohort, Conversion Funnel, LTV
- 🧪 **A/B 테스트**: 3가지 비즈니스 시나리오 실험 설계 및 통계 검정
- 💾 **SQL 기반 분석**: PostgreSQL을 활용한 데이터 추출 및 정제
- 📈 **데이터 시각화**: Tableau/Power BI 대시보드 및 Python 차트
- 📝 **비즈니스 리포트**: 스토리텔링 기반 인사이트 전달

## 🎯 프로젝트 목표

1. **SQL 역량**: PostgreSQL 기반 데이터 추출, 정제, 파생변수 생성
2. **핵심 지표 이해**: 모바일 서비스 필수 지표 계산 및 해석
3. **실험 설계**: A/B 테스트 설계 및 통계적 검증
4. **시각화**: Tableau/Power BI 대시보드 구축
5. **커뮤니케이션**: 분석 결과를 비즈니스 팀에 효과적으로 전달

## 🏗️ 시스템 아키텍처

```
┌─────────────────────┐
│  Mobile App Logs    │
│  (Event Tracking)   │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│   PostgreSQL DB     │
│  - users            │
│  - events           │
│  - sessions         │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│   SQL Queries       │
│  (Data Extraction)  │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  Python Analysis    │
│  - Retention        │
│  - Cohort           │
│  - Funnel           │
│  - LTV              │
│  - A/B Testing      │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  Visualization      │
│  - Tableau/Power BI │
│  - Python Charts    │
└─────────────────────┘
```

## 🛠️ 기술 스택

### 데이터 처리
- **SQL**: PostgreSQL (데이터 추출 및 정제)
- **Python**: Pandas, NumPy (데이터 전처리 및 분석)
- **Jupyter Notebook**: 탐색적 데이터 분석 (EDA)

### 통계 분석
- **Python**: SciPy, StatsModels (통계 검정)
- **A/B Testing**: t-test, Chi-square test

### 시각화
- **Tableau / Power BI**: 대시보드 구축
- **Python**: Matplotlib, Seaborn, Plotly

### 데이터베이스
- **PostgreSQL**: 사용자 행동 로그 저장

## 📊 핵심 지표

### 1. Retention Rate (재방문율)
사용자가 앱을 다시 사용하는 비율을 측정합니다.

```python
# Day 1 Retention 계산 예시
retention_day1 = (재방문_사용자_수 / 신규_가입자_수) * 100
```

- **Day 1 Retention**: 가입 다음날 재방문율
- **Day 7 Retention**: 가입 7일 후 재방문율
- **Day 30 Retention**: 가입 30일 후 재방문율

### 2. Cohort Analysis (코호트 분석)
가입 시기별 사용자 그룹의 행동 패턴을 비교합니다.

### 3. Conversion Funnel (전환 퍼널)
사용자 여정의 각 단계별 전환율을 분석합니다.

```
회원가입 (100%) → 프로필 작성 (80%) → 첫 거래 (40%) → 재거래 (25%)
```

### 4. LTV (Lifetime Value)
사용자의 생애 가치를 예측합니다.

## 🧪 A/B 테스트 시나리오

### 시나리오 1: 푸시 알림 최적화
- **가설**: 개인화된 푸시 알림이 일반 푸시보다 재방문율을 높인다
- **측정 지표**: Day 1/7 Retention
- **통계 검정**: t-test

### 시나리오 2: 온보딩 플로우 개선
- **가설**: 간소화된 온보딩(3단계)이 기존(5단계)보다 첫 거래 전환율을 높인다
- **측정 지표**: 온보딩 완료율, 첫 거래 전환율
- **통계 검정**: Chi-square test

### 시나리오 3: 할인 이벤트 효과 분석
- **가설**: 10% 할인이 사용자 LTV를 증가시킨다
- **측정 지표**: 30일 LTV, 재구매율
- **통계 검정**: t-test

## 🚀 Quick Start

### Prerequisites

```bash
# Python 3.9 이상 필요
python --version

# PostgreSQL 설치
# Windows: https://www.postgresql.org/download/windows/
# Mac: brew install postgresql
```

### Installation

```bash
# 1. 저장소 클론
git clone https://github.com/ts6nqswnr8-sudo/UpstageDemo.git
cd UpstageDemo

# 2. 가상환경 생성 및 활성화
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# 3. 의존성 설치
pip install -r requirements.txt

# 4. PostgreSQL 데이터베이스 생성
createdb mobile_analytics
```

### Usage

```bash
# 1. 데이터베이스 스키마 생성
python scripts/create_schema.py

# 2. 가상 데이터 생성
python scripts/generate_data.py

# 3. Jupyter Notebook 실행
jupyter notebook

# 4. notebooks/ 디렉토리에서 분석 노트북 실행
# - 01_data_preprocessing.ipynb
# - 02_key_metrics.ipynb
# - 03_ab_testing.ipynb
# - 04_visualization.ipynb
```

## 📂 프로젝트 구조

```
UpstageDemo/
├── data/                      # 샘플 데이터
│   └── sample_data.csv
├── sql/                       # SQL 쿼리 모음
│   ├── retention.sql
│   ├── cohort.sql
│   └── funnel.sql
├── notebooks/                 # Jupyter Notebooks
│   ├── 01_data_preprocessing.ipynb
│   ├── 02_key_metrics.ipynb
│   ├── 03_ab_testing.ipynb
│   └── 04_visualization.ipynb
├── scripts/                   # Python 스크립트
│   ├── create_schema.py
│   ├── generate_data.py
│   └── analysis_utils.py
├── dashboards/                # 대시보드 스크린샷
│   ├── main_dashboard.png
│   └── cohort_dashboard.png
├── reports/                   # 분석 리포트
│   ├── analysis_report.pdf
│   └── presentation.pptx
├── docs/                      # 문서
│   ├── PRD.md
│   ├── TASKS.md
│   └── Ideation.md
└── README.md
```

## 📈 주요 분석 결과 (예시)

### Retention Analysis
- **Day 1 Retention**: 45%
- **Day 7 Retention**: 28%
- **Day 30 Retention**: 15%

### Cohort Insights
- 2024년 1월 코호트가 가장 높은 Retention (32%)
- iOS 사용자가 Android 대비 20% 높은 Retention

### A/B Test Results
- **푸시 알림 최적화**: 개인화 푸시로 Day 1 Retention 8% 증가 (p < 0.01)
- **온보딩 개선**: 간소화된 온보딩으로 첫 거래 전환율 15% 증가 (p < 0.05)
- **할인 이벤트**: 10% 할인으로 30일 LTV 12% 증가 (p < 0.05)

## 🗓️ 개발 로드맵

- [x] **Phase 1**: 데이터 인프라 구축 (Week 1-2)
- [ ] **Phase 2**: 핵심 지표 계산 (Week 3-4)
- [ ] **Phase 3**: A/B 테스트 프레임워크 (Week 5-6)
- [ ] **Phase 4**: 시각화 및 대시보드 (Week 7-8)

자세한 작업 내용은 [TASKS.md](docs/TASKS.md)를 참조하세요.

## 📝 문서

- [PRD (Product Requirements Document)](docs/PRD.md)
- [작업 체크리스트 (TASKS)](docs/TASKS.md)
- [프로젝트 아이디어 (Ideation)](docs/Ideation.md)

## 🎓 토스뱅크 데이터 분석가 요구사항 매핑

| 요구사항 | 프로젝트 반영 |
|---------|-------------|
| SQL 기반 데이터 추출·정제 | PostgreSQL 쿼리 작성, 데이터 전처리 |
| 데이터 전처리 → 인사이트 도출 | 전체 분석 파이프라인 구현 |
| 데이터 시각화 툴 | Tableau/Power BI 대시보드 구축 |
| 모바일 서비스 지표 이해 | Retention, LTV, Cohort, Funnel 분석 |
| A/B 테스트 설계·검증 | 3가지 시나리오 A/B 테스트 수행 |
| 비즈니스 커뮤니케이션 | 스토리텔링 기반 리포트 작성 |
| Python/R 통계분석 (우대) | Python 통계 검정 및 분석 |
| 데이터 파이프라인 설계 (우대) | SQL → Python → 시각화 파이프라인 |

## 🤝 기여

이슈와 PR을 환영합니다! 자세한 내용은 [GitHub Issues](https://github.com/ts6nqswnr8-sudo/UpstageDemo/issues)를 참조하세요.

## 📄 라이선스

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📧 Contact

프로젝트에 대한 질문이나 제안사항이 있으시면 [GitHub Issues](https://github.com/ts6nqswnr8-sudo/UpstageDemo/issues)를 통해 연락주세요.

---

**Built for Toss Bank Data Analyst Portfolio**
