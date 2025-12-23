# 프로젝트 태스크: Dynamic Pricing & Sales Forecast Agent

[PRD](PRD.md) 기반 작업 리스트.

## Phase 1: 데이터 및 환경 설정
- [ ] **합성 데이터 생성 (Synthetic Data Generation)**
    - [ ] 일별 판매량 데이터 생성 스크립트 작성 (가격, 계절성, 노이즈 포함).
    - [ ] Ground Truth 인과 효과(가격 -> 판매량) 포함 여부 확인.
- [ ] **환경 설정 (Environment Setup)**
    - [ ] 의존성 라이브러리 설치: `torch`, `neuralforecast`, `econml`, `streamlit`, `pandas`, `numpy`.
    - [ ] 프로젝트 구조 및 디렉토리 설정.

## Phase 2: 모델링 (예측 및 인과 추론)
- [ ] **시계열 예측 모델 (Forecasting Model - Baseline & SOTA)**
    - [ ] Baseline 모델 학습 (예: ARIMA 또는 간단한 ML 모델).
    - [ ] 딥러닝 모델 학습 (NeuralForecast 활용 PatchTST).
    - [ ] 성능 평가 및 비교 (MAE/MSE).
- [ ] **인과 추론 모델 (Causal Inference Model)**
    - [ ] 인과 추론 모델 학습 (EconML 활용 Double ML 또는 Causal Forest).
    - [ ] 가격 탄력성(Price Elasticity) 산출.
    - [ ] CATE (조건부 평균 처치 효과) 추정 결과 및 Ground Truth 비교 검증.

## Phase 3: 애플리케이션 (시뮬레이션 대시보드)
- [ ] **Streamlit 대시보드 (Streamlit Dashboard)**
    - [ ] 값 조절 슬라이더(가격 변경)가 포함된 UI 레이아웃 구현.
    - [ ] 과거 데이터 및 미래 예측 시각화.
- [ ] **시뮬레이션 로직 (Simulation Logic)**
    - [ ] Counterfactual(반사실적) 추정 결과 UI 연동.
    - [ ] '기존 유지(Business as Usual)' vs '개입(Intervention)' 시나리오 비교 표시.
