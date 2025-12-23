# Causal Time Series Analysis & Forecasting System

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live-brightgreen)](https://ts6nqswnr8-sudo.github.io/UpstageDemo/)
[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> 시계열 예측과 인과 추론을 결합한 연구 중심 AI 시스템

## 📖 프로젝트 개요

**Causal Time Series Analysis & Forecasting System**은 최신 SOTA 시계열 예측 모델과 인과 추론 기술을 결합하여, 단순한 미래 예측을 넘어 **"만약 가격을 변경한다면?"**과 같은 반사실적(Counterfactual) 질문에 답할 수 있는 시스템입니다.

### 주요 특징

- 🤖 **최신 SOTA 모델**: PatchTST, iTransformer, TimeMixer, State-Space Models (Mamba)
- 🔬 **인과 추론**: DoWhy, EconML을 활용한 인과 효과 추정
- 📊 **자동화된 실험**: MLflow, Optuna를 통한 체계적인 실험 관리
- 🎯 **반사실적 시뮬레이션**: What-if 시나리오 분석
- 📈 **Interactive 대시보드**: Streamlit 기반 시각화

## 🎯 프로젝트 목표

1. **모델 벤치마킹**: 최신 시계열 모델들의 성능 비교 및 분석
2. **인과 효과 정량화**: 가격, 마케팅 등 변수 변화가 결과에 미치는 영향 측정
3. **설명 가능한 AI**: 예측 결과에 대한 인과적 설명 제공
4. **연구 역량 증명**: LG AI Research 인턴십 수준의 포트폴리오 구축

## 🏗️ 시스템 아키텍처

```
┌─────────────────────┐
│  Synthetic Data     │
│  Generation (DAG)   │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  Forecasting Models │
│  ├─ PatchTST        │
│  ├─ iTransformer    │
│  ├─ TimeMixer       │
│  └─ SSM (Mamba)     │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  Causal Inference   │
│  ├─ DoWhy           │
│  ├─ EconML          │
│  └─ Counterfactual  │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  Streamlit Dashboard│
│  & Visualization    │
└─────────────────────┘
```

## 🛠️ 기술 스택

### Core Technologies
- **Language**: Python 3.9+
- **Deep Learning**: PyTorch, TensorFlow
- **시계열 모델**: HuggingFace Transformers, NeuralForecast

### Causal Inference
- **Microsoft EconML**: Double ML, Causal Forest
- **DoWhy**: Causal graph modeling
- **CausalImpact**: Bayesian structural time-series

### Experiment & Optimization
- **MLflow**: Experiment tracking
- **Optuna**: Hyperparameter optimization
- **Ray Tune**: Distributed search

### Visualization
- **Streamlit**: Interactive dashboard
- **Matplotlib, Seaborn, Plotly**: Data visualization

## 🚀 Quick Start

### Prerequisites

```bash
# Python 3.9 이상 필요
python --version

# (Optional) GPU 사용 시 CUDA 설정
nvidia-smi
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
```

### Usage

```bash
# 1. 합성 데이터 생성
python scripts/generate_data.py

# 2. 모델 학습
python scripts/train_models.py --model patchTST

# 3. 인과 분석
python scripts/causal_analysis.py

# 4. 대시보드 실행
streamlit run app/dashboard.py
```

## 📂 프로젝트 구조

```
UpstageDemo/
├── docs/                      # 문서
│   ├── PRD.md                # Product Requirements Document
│   ├── TASKS.md              # 작업 체크리스트
│   ├── Ideation.md           # 프로젝트 아이디어
│   └── presentation.md       # Marp 프레젠테이션
├── src/                       # 소스 코드
│   ├── data/                 # 데이터 생성 및 처리
│   ├── models/               # 모델 구현
│   │   ├── baseline/         # ARIMA, XGBoost, LSTM
│   │   └── sota/             # PatchTST, iTransformer, etc.
│   ├── causal/               # 인과 추론 모듈
│   └── utils/                # 유틸리티 함수
├── scripts/                   # 실행 스크립트
├── app/                       # Streamlit 대시보드
├── experiments/               # 실험 결과
├── notebooks/                 # Jupyter notebooks
└── tests/                     # 테스트 코드
```

## 📊 주요 기능

### 1. 합성 데이터 생성
인과 관계가 명확한 시계열 데이터를 생성하여 모델 검증에 활용합니다.

```python
from src.data import SyntheticDataGenerator

generator = SyntheticDataGenerator(
    causal_graph={'price': ['demand'], 'seasonality': ['sales']}
)
data = generator.generate(n_samples=1000)
```

### 2. 시계열 예측
최신 SOTA 모델로 미래 값을 예측합니다.

```python
from src.models import PatchTST

model = PatchTST(input_dim=10, hidden_dim=128)
predictions = model.forecast(data, horizon=30)
```

### 3. 인과 효과 추정
특정 변수 변화가 결과에 미치는 영향을 정량화합니다.

```python
from src.causal import CausalAnalyzer

analyzer = CausalAnalyzer(method='econml')
ate = analyzer.estimate_ate(treatment='price', outcome='sales')
```

### 4. 반사실적 시뮬레이션
"만약 가격을 10% 올렸다면?"과 같은 시나리오를 시뮬레이션합니다.

```python
counterfactual = analyzer.simulate_counterfactual(
    intervention={'price': 1.1},  # 10% 인상
    data=data
)
```

## 📈 실험 결과

### 모델 성능 비교 (예시)

| Model        | MSE    | MAE   | RMSE  |
|-------------|--------|-------|-------|
| ARIMA       | 0.245  | 0.389 | 0.495 |
| XGBoost     | 0.198  | 0.321 | 0.445 |
| LSTM        | 0.176  | 0.298 | 0.420 |
| **PatchTST**    | **0.142**  | **0.265** | **0.377** |
| iTransformer| 0.151  | 0.278 | 0.389 |
| TimeMixer   | 0.148  | 0.271 | 0.385 |

### 인과 효과 추정 (예시)

- **Price Elasticity**: -0.85 (가격 1% 증가 시 수요 0.85% 감소)
- **ATE (Average Treatment Effect)**: -12.3 units
- **CATE 범위**: -8.5 ~ -15.2 units

## 🗓️ 개발 로드맵

- [x] **Phase 1**: 데이터 및 환경 구축
- [ ] **Phase 2**: 최신 모델 구현 및 벤치마킹
- [ ] **Phase 3**: 인과 추론 통합
- [ ] **Phase 4**: 대시보드 및 리포트

자세한 작업 내용은 [TASKS.md](docs/TASKS.md)를 참조하세요.

## 📝 문서

- [PRD (Product Requirements Document)](docs/PRD.md)
- [작업 체크리스트 (TASKS)](docs/TASKS.md)
- [프로젝트 아이디어 (Ideation)](docs/Ideation.md)
- [프레젠테이션 (GitHub Pages)](https://ts6nqswnr8-sudo.github.io/UpstageDemo/)

## 🤝 기여

이슈와 PR을 환영합니다! 자세한 내용은 [GitHub Issues](https://github.com/ts6nqswnr8-sudo/UpstageDemo/issues)를 참조하세요.

## 📄 라이선스

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- LG AI Research Data Intelligence Lab의 연구 방향성에서 영감을 받았습니다
- SOTA 시계열 모델 논문 및 오픈소스 구현체를 참고했습니다
- Microsoft EconML, DoWhy 팀에 감사드립니다

## 📧 Contact

프로젝트에 대한 질문이나 제안사항이 있으시면 [GitHub Issues](https://github.com/ts6nqswnr8-sudo/UpstageDemo/issues)를 통해 연락주세요.

---

**Built with ❤️ for LG AI Research Internship Application**
