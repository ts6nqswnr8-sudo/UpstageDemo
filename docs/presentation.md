---
marp: true
theme: gaia
paginate: true
backgroundColor: #fff
style: |
  section {
    font-family: 'Malgun Gothic', 'Apple SD Gothic Neo', sans-serif;
  }
---

# Dynamic Pricing & Sales Forecast Agent

**목표**: 시계열 예측과 인과 추론 기술을 결합하여, 가격 변화에 따른 판매량 변화를 시뮬레이션하고 최적의 가격 정책을 제안하는 로컬 AI 에이전트 개발.

---

# 2. 해결하고자 하는 문제

- **단순 예측의 한계**:
  - 기존 시계열 모델은 과거 패턴 기반으로 예측.
  - "가격을 올리면 어떻게 될까?" 같은 **개입(Intervention)**에 대한 답을 주지 못함.

- **비즈니스 의사결정 지원**:
  - 마케팅이나 가격 정책 변경 전, 결과를 데이터 기반으로 미리 시뮬레이션할 도구 필요.

---

# 3. 핵심 기능 (MVP Scope)

1. **합성 데이터 생성 (Data Generation)**
   - 인과 관계(가격 $\uparrow$ $\to$ 수요 $\downarrow$)가 내재된 합성 데이터 생성.
   - Ground Truth를 통한 검증 용이성 확보.

2. **시계열 예측 (Forecasting Module)**
   - **PatchTST** 또는 **NeuralForecast** (Transformer 기반 SOTA).
   - 베이스라인(ARIMA/XGBoost) 대비 딥러닝 모델 성능 비교.

3. **인과 효과 추론 (Causal Inference Module)**
   - **EconML** 또는 **DoWhy**.
   - 가격 탄력성 산출 및 반사실적(Counterfactual) 추론.

4. **시뮬레이션 대시보드 (Streamlit UI)**
   - 미래 가격 변동폭 조절 가능한 Interactive Slider.
   - [기존 가격 유지 시 예측] vs [가격 변경 시 예측] 비교 그래프.

---

# 4. 기술 스택

- **Language**: Python 3.9+
- **Forecasting**: PyTorch, HuggingFace, NeuralForecast (PatchTST)
- **Causal Inference**: Microsoft EconML (Double ML, Causal Forest 등)
- **Visualization**: Streamlit, Matplotlib/Plotly
- **Data**: Pandas, Numpy

---

# 5. 데이터 흐름

1. **Data Generation**: 가격, 계절성, 노이즈가 섞인 일별 판매량 데이터 생성.
2. **Forecasting Model**: 과거 데이터를 학습하여 미래 30일 판매량 예측 (Baseline).
3. **Causal Model**: 가격(Treatment)과 판매량(Outcome) 간의 관계 학습 ($Y = f(T, X)$).
4. **Simulation**: 사용자가 입력한 가격($T'$)을 Causal Model에 대입하여 새로운 판매량($Y'$) 예측.
5. **Visualization**: $Y$와 $Y'$를 대시보드에 시각화.

---

# 6. 개발 로드맵

1. **Phase 1: 데이터 및 환경**
   - 합성 데이터 생성 스크립트 작성.
   - ML 환경 설정 (PyTorch, EconML).

2. **Phase 2: 모델링**
   - 시계열 예측 모델 학습 및 평가.
   - 인과 추론 모델 학습 (CATE 추정).

3. **Phase 3: 애플리케이션**
   - Streamlit 대시보드 구현.
   - 시나리오 시뮬레이션 기능 연동.
