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

# Causal Time Series Analysis & Forecasting System

**시계열 예측과 인과 추론을 결합한 연구 중심 AI 시스템**

LG AI Research Data Intelligence Lab 지원 포트폴리오

---

## 📌 프로젝트 개요

**목표**: 최신 시계열 예측 모델과 인과 추론 기술을 결합하여, 반사실적(Counterfactual) 시나리오 분석이 가능한 연구 중심 AI 시스템 개발

**핵심 가치**:
- 단순 예측을 넘어 **"만약 ~했다면?"** 질문에 답함
- 인과 관계 기반 **설명 가능한 AI**
- Top-tier 학회 수준의 **실험 설계 및 분석**

---

## 🎯 해결하고자 하는 문제

### 1. 단순 예측의 한계
- 기존 모델: 과거 패턴 기반 예측만 가능
- **개입(Intervention)** 질문에 답하지 못함
  - "가격을 올리면 어떻게 될까?"
  - "마케팅 예산을 늘리면?"

### 2. 인과 관계 이해 부족
- 상관관계 ≠ 인과관계
- 블랙박스 모델의 설명력 부족

### 3. 연구 역량 증명 필요
- 체계적인 실험 설계
- 재현 가능한 결과
- 포트폴리오 수준의 문서화

---

## 🔬 핵심 기능 (MVP Scope)

### 1. 합성 데이터 생성
- 인과 그래프(DAG) 기반 데이터 생성
- Ground Truth 검증 가능
- 계절성, 트렌드, 노이즈, 외부 충격 포함

### 2. SOTA 시계열 예측 모델
- **PatchTST**: Transformer 기반 패치 단위 모델
- **iTransformer**: Inverted Transformer
- **TimeMixer**: Multi-scale mixing
- **SSM (Mamba)**: State-Space Models

---

## 🔬 핵심 기능 (계속)

### 3. 인과 추론 모듈
- **DoWhy**: 인과 그래프 모델링
- **EconML**: Double ML, Causal Forest
- **효과 추정**: ATE, CATE, Price Elasticity
- **반사실적 추론**: Counterfactual 시뮬레이션

### 4. 자동화된 실험 프레임워크
- **MLflow**: 실험 트래킹
- **Optuna**: 하이퍼파라미터 최적화
- 재현 가능한 실험 설계

### 5. Interactive 대시보드
- **Streamlit** 기반 시각화
- 실시간 시나리오 시뮬레이션

---

## 🛠️ 기술 스택

### Core Technologies
- **Python 3.9+**, PyTorch, TensorFlow
- HuggingFace Transformers, NeuralForecast

### Causal Inference
- Microsoft **EconML**, **DoWhy**, CausalImpact

### Experiment & Optimization
- **MLflow**, **Optuna**, Ray Tune

### Visualization
- **Streamlit**, Matplotlib, Seaborn, Plotly

---

## 📊 데이터 흐름

```
1. Synthetic Data Generation (DAG 기반)
   ↓
2. Data Preprocessing & Feature Engineering
   ↓
3. Forecasting Models Training
   (PatchTST, iTransformer, TimeMixer, SSM)
   ↓
4. Model Evaluation & Comparison
   ↓
5. Causal Inference Analysis
   (ATE/CATE 추정, Counterfactual)
   ↓
6. Visualization & Reporting
```

---

## 🎓 연구 목표 및 성과 지표

### 연구 목표
- 최신 시계열 모델 벤치마킹
- 인과 효과 정량화
- 설명 가능한 예측 시스템

### 성과 지표
- **예측 정확도**: 베이스라인 대비 개선율
- **인과 추정 정확도**: Ground Truth 대비 오차
- **재현 가능성**: 모든 실험 재현 가능
- **포트폴리오 품질**: 논문 수준의 리포트

---

## 🗓️ 개발 로드맵

### Phase 1: 데이터 및 환경 구축 (Week 1-2)
- 합성 데이터 생성 (인과 그래프 기반)
- ML 환경 설정 (PyTorch, EconML, Optuna)
- 베이스라인 모델 (ARIMA, XGBoost, LSTM)

### Phase 2: 최신 모델 구현 (Week 3-4)
- PatchTST, iTransformer, TimeMixer, SSM 구현
- 자동화된 실험 파이프라인
- 모델 성능 비교 및 분석

---

## 🗓️ 개발 로드맵 (계속)

### Phase 3: 인과 추론 통합 (Week 5-6)
- DoWhy/EconML 인과 그래프 정의
- ATE/CATE 추정 및 검증
- 반사실적 시뮬레이션

### Phase 4: 대시보드 및 리포트 (Week 7-8)
- Streamlit 대시보드 구현
- 실험 결과 시각화
- 포트폴리오 문서화

---

## 💡 기대 효과 및 활용

### 연구 역량 증명
- Top-tier 학회(NeurIPS, ICLR, ICML) 수준의 실험 설계
- 최신 시계열 모델 깊은 이해 및 구현

### 실무 적용 가능성
- 소매/제조/금융 등 다양한 산업 활용
- 가격 최적화, 수요 예측, 재고 관리

### LG AI Research 적합성
- Data Intelligence Lab 연구 방향 완벽 부합
- 시계열, 인과추론, 최적화 통합

---

## 📈 예상 결과 (예시)

### 모델 성능 비교
| Model | MSE | MAE | RMSE |
|-------|-----|-----|------|
| ARIMA | 0.245 | 0.389 | 0.495 |
| LSTM | 0.176 | 0.298 | 0.420 |
| **PatchTST** | **0.142** | **0.265** | **0.377** |

### 인과 효과 추정
- **Price Elasticity**: -0.85
- **ATE**: -12.3 units
- **추정 정확도**: Ground Truth 대비 ±5%

---

## 🎯 차별화 포인트

✅ **최신 SOTA 모델** 4종 통합 비교
✅ **인과 추론** 기반 설명 가능한 AI
✅ **자동화된 실험** 프레임워크 (MLflow + Optuna)
✅ **재현 가능성** 100% 보장
✅ **포트폴리오 품질** 논문 수준 문서화
✅ **Interactive 대시보드** 실시간 시뮬레이션

---

## 📚 참고 자료

- **GitHub Repository**: [UpstageDemo](https://github.com/ts6nqswnr8-sudo/UpstageDemo)
- **Documentation**: PRD, TASKS, README
- **GitHub Pages**: [Live Presentation](https://ts6nqswnr8-sudo.github.io/UpstageDemo/)

---

## 🙏 Thank You!

**Questions?**

GitHub: [ts6nqswnr8-sudo/UpstageDemo](https://github.com/ts6nqswnr8-sudo/UpstageDemo)

**Built with ❤️ for LG AI Research Internship Application**
