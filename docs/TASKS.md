# Task List: Causal Time Series Analysis & Forecasting System

## Phase 1: 데이터 및 환경 구축 (Week 1-2)

### 환경 설정
- [ ] Python 3.9+ 가상환경 생성
- [ ] PyTorch 설치 및 CUDA 설정 (GPU 사용 시)
- [ ] 필수 라이브러리 설치
  - [ ] EconML, DoWhy
  - [ ] Optuna, Ray Tune
  - [ ] MLflow
  - [ ] Streamlit
  - [ ] Pandas, NumPy, Matplotlib, Seaborn, Plotly

### 합성 데이터 생성
- [ ] 인과 그래프 정의 (DAG)
  - [ ] Price → Demand 관계
  - [ ] Seasonality → Sales 관계
  - [ ] Marketing → Sales 관계
- [ ] 합성 데이터 생성 스크립트 작성
  - [ ] 계절성 패턴 구현
  - [ ] 트렌드 구현
  - [ ] 노이즈 추가
  - [ ] 외부 충격(Shock) 시뮬레이션
- [ ] Ground Truth 인과 효과 기록
- [ ] 데이터 검증 및 시각화

### 베이스라인 모델
- [ ] ARIMA 모델 구현
- [ ] XGBoost 모델 구현
- [ ] LSTM 모델 구현
- [ ] 베이스라인 성능 측정 (MSE, MAE, RMSE)

## Phase 2: 최신 모델 구현 및 벤치마킹 (Week 3-4)

### 모델 구현
- [ ] PatchTST 구현
  - [ ] 모델 아키텍처 구현
  - [ ] 학습 파이프라인 구성
  - [ ] 하이퍼파라미터 설정
- [ ] iTransformer 구현
  - [ ] Inverted Transformer 아키텍처 구현
  - [ ] 학습 파이프라인 구성
- [ ] TimeMixer 구현
  - [ ] Multi-scale mixing 구현
  - [ ] 학습 파이프라인 구성
- [ ] State-Space Models (SSM) 구현
  - [ ] Mamba/S-Mamba 아키텍처 구현
  - [ ] 학습 파이프라인 구성

### 자동화된 실험 프레임워크
- [ ] 실험 설정 파일 구조 설계 (YAML/JSON)
- [ ] MLflow 실험 트래킹 설정
  - [ ] 메트릭 로깅
  - [ ] 파라미터 로깅
  - [ ] 모델 아티팩트 저장
- [ ] Optuna 하이퍼파라미터 탐색 구현
  - [ ] 탐색 공간 정의
  - [ ] 목적 함수 정의
  - [ ] 최적화 실행
- [ ] 모델 비교 자동화 스크립트
  - [ ] 동일 조건 학습
  - [ ] 성능 메트릭 수집
  - [ ] 결과 저장

### 모델 평가
- [ ] Train/Validation/Test 분할 (시계열 고려)
- [ ] 각 모델 학습 및 평가
- [ ] 성능 비교 표 생성
- [ ] 예측 시각화 (실제 vs 예측)
- [ ] 장기 의존성(Long-term Dependency) 분석

## Phase 3: 인과 추론 통합 (Week 5-6)

### 인과 그래프 및 모델링
- [ ] DoWhy를 활용한 인과 그래프 정의
- [ ] 인과 가정 검증 (Backdoor, Frontdoor)
- [ ] EconML 모델 선택
  - [ ] Double ML
  - [ ] Causal Forest
  - [ ] DML (Debiased Machine Learning)

### 효과 추정
- [ ] ATE (Average Treatment Effect) 추정
- [ ] CATE (Conditional Average Treatment Effect) 추정
- [ ] Price Elasticity 계산
- [ ] 신뢰구간 산출
- [ ] Ground Truth 대비 추정 오차 계산

### 반사실적 추론
- [ ] Counterfactual 시나리오 정의
  - [ ] "가격 10% 인상 시" 시뮬레이션
  - [ ] "마케팅 예산 증가 시" 시뮬레이션
- [ ] 반사실적 예측 구현
- [ ] Treatment vs Control 비교 시각화
- [ ] 민감도 분석 (Sensitivity Analysis)

## Phase 4: 대시보드 및 리포트 (Week 7-8)

### Streamlit 대시보드
- [ ] 대시보드 레이아웃 설계
- [ ] 모델 선택 UI 구현
- [ ] 예측 결과 시각화
  - [ ] 시계열 그래프
  - [ ] 모델별 비교 차트
- [ ] 인과 효과 시각화
  - [ ] Treatment Effect 그래프
  - [ ] Counterfactual 비교
- [ ] Interactive Slider 구현
  - [ ] 가격 조절
  - [ ] 마케팅 예산 조절
  - [ ] 실시간 예측 업데이트
- [ ] 성능 메트릭 대시보드

### 연구 리포트 생성
- [ ] 실험 결과 요약 테이블 자동 생성
- [ ] 모델 비교 그래프 생성
- [ ] 인과 효과 분석 리포트
- [ ] 논문 수준의 Figure 생성
- [ ] LaTeX 표 생성 (선택)

### 문서화
- [ ] README.md 작성
  - [ ] 프로젝트 개요
  - [ ] 설치 방법
  - [ ] 사용 방법
  - [ ] 실험 결과
- [ ] 코드 주석 및 Docstring
- [ ] 실험 노트 정리
- [ ] 포트폴리오 문서 작성

## 추가 작업

### 코드 품질
- [ ] 코드 리팩토링
- [ ] 유닛 테스트 작성
- [ ] 타입 힌팅 추가
- [ ] Linting (flake8, black)

### 재현 가능성
- [ ] requirements.txt 생성
- [ ] Docker 컨테이너 설정 (선택)
- [ ] 랜덤 시드 고정
- [ ] 실험 재현 스크립트

### 확장 기능 (선택)
- [ ] 실제 데이터셋 적용 (Kaggle 등)
- [ ] 추가 모델 구현
- [ ] 앙상블 기법 적용
- [ ] 온라인 학습 기능
