# MVP 제안: Causal Time Series Analyzer

LG AI Research 등에서 연구 중인 **시계열 예측(Time Series Forecasting)**과 **인과 추론(Causal Inference)**을 결합한 로컬 MVP 프로젝트입니다.

## 🎯 프로젝트명: **Dynamic Pricing & Sales Forecast Agent**

가장 직관적으로 인과 효과(가격 $\to$ 판매량)를 분석할 수 있는 **"소매점 판매량 예측 및 가격 최적화"** 시나리오를 제안합니다.

### 📌 기획 의도
- **Core Challenge**: 단순 미래 예측(Forecasting)을 넘어, "가격을 올리면 판매량이 얼마나 줄어들까?"라는 **반사실적(Counterfactual) 질문**에 답해야 함.
- **Tech Hybrid**: SOTA 시계열 모델(PatchTST)과 인과 추론 라이브러리(DoWhy/EconML)를 결합.
- **Business Value**: AI가 의사결정(Intervention)의 결과를 시뮬레이션해주는 Agent.

---

### 🛠️ 기능 명세 (Feature Spec)

#### 1. 데이터 파이프라인 (Data Pipeline)
- **데이터셋**: Kaggle Store Sales 등 공공 데이터 또는 트렌드/계절성/가격탄력성이 포함된 **합성 데이터(Synthetic Data)** 생성 (인과 검증 용이성 위해 초기엔 합성 데이터 추천).
- **전처리**: 결측치 처리, 윈도우 슬라이딩(Window Sliding).

#### 2. 시계열 예측 모듈 (Forecasting Module)
- **Baseline**: ARIMA 또는 XGBoost.
- **Deep Learning**: **PatchTST** (Transformer 기반) 또는 **DLinear**.
- **역할**: "특별한 개입이 없을 때(Business as usual)" 미래 판매량 예측.

#### 3. 인과 추론 모듈 (Causal Inference Module)
- **라이브러리**: **DoWhy** 또는 **EconML**.
- **Causal Graph**: `Price -> Sales`, `Seasonality -> Sales`, `Marketing -> Sales` 등의 인과 그래프 정의.
- **Effect Estimation**: 가격 변화에 따른 판매량 변화율(ATE/CATE) 추정.

#### 4. 시나리오 시뮬레이터 (Intervention Dashboard)
- **UI**: Streamlit.
- **기능**:
    - "내일 가격을 10% 올리면 매출총이익은 어떻게 될까?" 시뮬레이션.
    - 예측 그래프와 반사실적(Counterfactual) 그래프 비교 시각화.

---

### 📚 기술 스택
- **Language**: Python 3.9+
- **Forecasting**: PyTorch, HuggingFace (PatchTST implementation), NeuralForecast
- **Causal**: Microsoft EconML (Double ML 등 강력한 추정기 제공) 또는 DoWhy
- **Analysis**: Pandas, Matplotlib

### 📅 개발 로드맵
1.  **데이터 준비**: 인과 관계가 명확한 합성 데이터 생성 (가격 $\uparrow$ $\to$ 판매 $\downarrow$)
2.  **예측 모델링**: PatchTST 등을 활용한 베이스라인 예측 성능 확보
3.  **인과 분석**: EconML을 사용하여 가격 탄력성(Elasticity) 산출
4.  **통합 시뮬레이터**: "가격 슬라이더"를 움직이면 예상 매출 그래프가 변하는 UI 구현

이 시나리오(가격 결정 및 수요 예측)가 연구실의 기술 스택을 실험하기에 적합해 보입니다. 이 방향으로 진행할까요?
