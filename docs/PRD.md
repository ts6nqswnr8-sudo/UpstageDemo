# Product Requirements Document (PRD): Causal Time Series Analysis & Forecasting System

## 1. 프로젝트 개요
**프로젝트명**: Causal Time Series Analysis & Forecasting System  
**목표**: 최신 시계열 예측 모델과 인과 추론 기술을 결합하여, 반사실적(Counterfactual) 시나리오 분석이 가능한 연구 중심 AI 시스템 개발. LG AI Research Data Intelligence Lab의 연구 방향성에 부합하는 포트폴리오 수준의 프로젝트.

## 2. 해결하고자 하는 문제
- **단순 예측의 한계**: 기존 시계열 모델은 과거 패턴 기반 예측만 가능하며, "특정 변수를 변경하면 어떻게 될까?"라는 **개입(Intervention)** 질문에 답하지 못함.
- **인과 관계 이해 부족**: 상관관계는 파악하지만 인과관계(Causality)를 명확히 설명하지 못하는 블랙박스 문제.
- **연구 역량 증명**: Top-tier 학회 수준의 실험 설계, 모델 비교, 성능 분석 능력을 보여줄 수 있는 체계적인 프로젝트 필요.

## 3. 핵심 기능 (MVP Scope)

### 3.1 합성 데이터 생성 (Synthetic Data Generation)
- **인과 그래프 기반 데이터 생성**: 명확한 인과 관계(Price → Demand, Seasonality → Sales 등)가 내재된 시계열 데이터 생성.
- **Ground Truth 검증**: 생성된 데이터의 실제 인과 효과를 알고 있어 모델 성능 검증 용이.
- **다양한 시나리오**: 계절성, 트렌드, 노이즈, 외부 충격(Shock) 등 다양한 패턴 포함.

### 3.2 최신 시계열 예측 모델 벤치마킹 (SOTA Forecasting Models)
- **구현 모델**:
  - **PatchTST**: Transformer 기반 패치 단위 시계열 모델
  - **iTransformer**: Inverted Transformer 아키텍처
  - **TimeMixer**: Multi-scale mixing 기반 모델
  - **State-Space Models (SSM)**: Mamba/S-Mamba 등 최신 SSM 아키텍처
- **베이스라인 비교**: ARIMA, XGBoost, LSTM 등 전통적 모델 대비 성능 비교.
- **평가 지표**: MSE, MAE, RMSE, MAPE 등 다양한 메트릭으로 정량 평가.

### 3.3 인과 추론 모듈 (Causal Inference Module)
- **라이브러리**: Microsoft EconML, DoWhy, CausalImpact.
- **인과 그래프 정의**: DAG(Directed Acyclic Graph)를 통한 변수 간 인과 관계 명시.
- **효과 추정**:
  - **ATE (Average Treatment Effect)**: 평균 처치 효과
  - **CATE (Conditional Average Treatment Effect)**: 조건부 평균 처치 효과
  - **Price Elasticity**: 가격 탄력성 산출
- **반사실적 추론**: "만약 X를 변경했다면 Y는 어떻게 되었을까?" 시뮬레이션.

### 3.4 자동화된 실험 프레임워크 (Automated Experiment Pipeline)
- **하이퍼파라미터 탐색**: Optuna 또는 Ray Tune을 활용한 자동 튜닝.
- **모델 비교 자동화**: 여러 모델을 동일 조건에서 학습 및 평가.
- **재현 가능성**: 실험 설정, 랜덤 시드, 결과를 체계적으로 기록.

### 3.5 시각화 및 대시보드 (Visualization & Dashboard)
- **Streamlit 기반 대시보드**:
  - 모델별 예측 결과 비교 그래프
  - 인과 효과 시각화 (Treatment vs Control)
  - Interactive Slider로 개입 변수 조절 및 실시간 시뮬레이션
- **연구 리포트 생성**: 실험 결과를 논문 수준의 표와 그래프로 자동 생성.

## 4. 기술 스택

### 4.1 Core Technologies
- **Language**: Python 3.9+
- **Deep Learning Framework**: PyTorch, TensorFlow
- **시계열 모델**: 
  - HuggingFace Transformers (PatchTST)
  - NeuralForecast
  - Custom implementations (iTransformer, TimeMixer, SSM)

### 4.2 Causal Inference
- **Microsoft EconML**: Double ML, Causal Forest, DML
- **DoWhy**: Causal graph modeling, effect estimation
- **CausalImpact**: Bayesian structural time-series models

### 4.3 Experiment & Optimization
- **Optuna**: Hyperparameter optimization
- **Ray Tune**: Distributed hyperparameter search
- **MLflow**: Experiment tracking

### 4.4 Data & Visualization
- **Pandas, NumPy**: Data manipulation
- **Matplotlib, Seaborn, Plotly**: Visualization
- **Streamlit**: Interactive dashboard

## 5. 데이터 흐름 (Data Flow)

```
1. Synthetic Data Generation
   ↓
2. Data Preprocessing & Feature Engineering
   ↓
3. Train/Test Split (시계열 고려)
   ↓
4. Forecasting Models Training
   ├─ PatchTST
   ├─ iTransformer
   ├─ TimeMixer
   └─ SSM (Mamba)
   ↓
5. Model Evaluation & Comparison
   ↓
6. Causal Inference Analysis
   ├─ Causal Graph Definition
   ├─ Effect Estimation (ATE/CATE)
   └─ Counterfactual Simulation
   ↓
7. Visualization & Reporting
```

## 6. 연구 목표 및 성과 지표

### 6.1 연구 목표
- **모델 성능 비교**: 최신 시계열 모델들의 장단점 분석 및 벤치마킹.
- **인과 효과 정량화**: 특정 변수 변화가 결과에 미치는 영향을 수치로 증명.
- **설명 가능성**: 예측 결과에 대한 인과적 설명 제공.

### 6.2 성과 지표
- **예측 정확도**: MSE, MAE 기준 베이스라인 대비 X% 개선.
- **인과 효과 추정 정확도**: Ground Truth 대비 추정 오차 Y% 이내.
- **재현 가능성**: 모든 실험 결과 재현 가능한 코드 및 문서 제공.
- **포트폴리오 품질**: 논문 수준의 실험 리포트 및 시각화 자료 생성.

## 7. 개발 로드맵

### Phase 1: 데이터 및 환경 구축 (Week 1-2)
- 합성 데이터 생성 스크립트 작성 (인과 그래프 기반).
- ML 환경 설정 (PyTorch, EconML, Optuna).
- 베이스라인 모델 구현 (ARIMA, XGBoost).

### Phase 2: 최신 모델 구현 및 벤치마킹 (Week 3-4)
- PatchTST, iTransformer, TimeMixer, SSM 구현.
- 자동화된 실험 파이프라인 구축.
- 모델별 성능 비교 및 분석.

### Phase 3: 인과 추론 통합 (Week 5-6)
- DoWhy/EconML을 활용한 인과 그래프 정의.
- ATE/CATE 추정 및 검증.
- 반사실적 시뮬레이션 구현.

### Phase 4: 대시보드 및 리포트 (Week 7-8)
- Streamlit 대시보드 구현.
- 실험 결과 시각화 및 자동 리포트 생성.
- 포트폴리오 문서화 (README, 실험 노트, 결과 분석).

## 8. 기대 효과 및 활용

### 8.1 연구 역량 증명
- Top-tier 학회(NeurIPS, ICLR, ICML) 수준의 실험 설계 및 분석 능력 시연.
- 최신 시계열 모델에 대한 깊은 이해 및 구현 경험.

### 8.2 실무 적용 가능성
- 소매/제조/금융 등 다양한 산업에서 의사결정 지원 도구로 활용.
- 가격 최적화, 수요 예측, 재고 관리 등 실제 비즈니스 문제 해결.

### 8.3 LG AI Research 적합성
- Data Intelligence Lab의 연구 방향(시계열, 인과추론, 최적화)과 완벽히 부합.
- 인턴십 지원 시 강력한 포트폴리오로 활용 가능.
