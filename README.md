# 품질 이상 탐지 분석

<br/>

<code><img height = '450'
src = https://github.com/user-attachments/assets/e9a8b901-98df-4447-b345-52b4d8523ca7></code>


<br/>

## 프로젝트 개요
이번 프로젝트는 **KAMP (Korea AI Manufacturing Platform)** 에서 제공하는 크로메이트 공정 데이터를 활용하여, 품질 이상 탐지 및 진단을 통해 스마트 팩토리의 품질 관리 프로세스를 혁신하는 것을 목표로 했습니다.  
이 프로젝트는 제조 공정에서 센서 데이터를 활용한 품질 관리 방안을 분석하고, 이상 탐지 모델을 구축함으로써 생산성 향상과 불량률 감소를 목표로 하였습니다.

---

## 주요 데이터
- **온도 (Temperature)**: 공정 과정의 온도 (°C)
- **pH**: 화학 용액의 산도 (0~14)
- **압력 (Pressure)**: 공정 중 발생한 압력 (kPa)
- **품질 상태 (Quality Output)**: 정상 / 이상 여부를 나타내는 레이블

### 데이터 특징
1. **데이터셋**: KAMP 데이터셋  
   - **크기**: 약 911MB, 총 302,115개 데이터 포인트
   - **형태**: CSV 파일
2. **특징**:  
   - 온도와 pH 값은 품질 이상과 밀접한 연관이 있으며, 주요 변수 간 상호작용이 복잡한 구조를 보임.

---

## 프로젝트 목표
### 1. 품질 이상 탐지
- **목적**: 생산 공정의 이상 데이터를 조기에 탐지하여 문제를 예방합니다.
- **방법**:  
  - AutoEncoder 및 Isolation Forest를 사용하여 이상치 탐지 모델을 구축.
  - Decision Tree를 활용하여 주요 품질 이상 발생 지점을 도출.

### 2. 품질 이상 원인 진단
- **목적**: 이상 발생 원인을 분석하여 공정 효율성을 높입니다.
- **방법**: 주요 변수(pH, 온도, 압력)와 품질 결과 간 상관관계 분석.

### 3. 분석 자동화
- **목적**: 데이터 수집부터 분석 및 결과 도출까지의 과정을 자동화.
- **방법**: Python과 Jupyter Notebook을 기반으로 분석 파이프라인 구축.

### 4. 기대 효과
- **생산성 향상**: 품질 이상 조기 탐지로 생산 공정 최적화.
- **불량률 감소**: 공정 이상으로 인한 제품 불량 최소화.
- **의사결정 지원**: 데이터를 기반으로 한 전략적 공정 개선 가능.

---

## 데이터 전처리 및 분석
### 1. 데이터 전처리
- **결측값 처리**: 평균 대체, 중앙값 대체.
- **이상치 제거**: IQR (Interquartile Range) 및 Z-score 방법.
- **데이터 정규화**: Min-Max Scaling으로 변수 간 스케일 조정.

### 2. 탐색적 데이터 분석 (EDA)
- 데이터 분포 확인: 히스토그램, 박스플롯.
- 변수 간 상관관계 분석: 히트맵 시각화.

### 3. 이상 탐지 모델 구축
- **모델링**:
  - Isolation Forest: 이상치 탐지.
  - AutoEncoder: 비지도 학습 기반 이상 패턴 탐지.
- **딥러닝 모델**:
  - TensorFlow 기반 CNN 모델로 이미지 데이터 분석.

### 4. 결과 분석 및 평가
- **성능 지표**:
  - Precision, Recall, F1-Score로 모델 평가.
- **결과 시각화**:
  - ROC Curve 및 Confusion Matrix를 통한 모델 성능 분석.

---

## 결과 및 인사이트
1. **주요 발견**:
   - 불량률은 특정 온도 범위(70~80°C)에서 급격히 증가.
   - 압력과 pH 값의 조합이 품질에 중요한 영향을 미침.

2. **적용 방안**:
   - 조기 경고 시스템 설계: 실시간 공정 이상 탐지 및 경고 발송.
   - 최적 공정 조건 도출: 온도 75~78°C, 압력 950~1000kPa로 유지 권장.

---

## 사용된 기술 스택
- **언어 및 도구**: Python, Jupyter Notebook
- **라이브러리**:
  - 데이터 처리: `pandas`, `numpy`
  - 시각화: `matplotlib`, `seaborn`
  - 머신러닝: `scikit-learn`, `tensorflow`
  - AutoML: `AutoKeras`

---

<br/>

## 프로젝트 리뷰: 배운 점과 인사이트

이번 프로젝트는 데이터를 통해 문제를 해결하는 과정에서 많은 것을 배울 수 있는 소중한 경험이었습니다. 특히 주니어 데이터 분석가로서 데이터를 다루는 기본부터 머신러닝 모델을 적용하기까지, 실제 분석 과정에서 얻은 인사이트를 공유하고 싶습니다.

처음 데이터를 봤을 땐 그저 숫자들의 나열처럼 보였지만, 전처리와 시각화를 통해 데이터를 이해하는 과정이 정말 중요하다는 걸 느꼈습니다.  
예를 들어, **온도와 불량률의 상관관계**를 발견했을 때, 단순한 데이터셋이 공정의 핵심적인 문제를 설명할 수 있다는 점이 흥미로웠습니다.  
이 프로젝트를 통해 데이터를 해석하고 숨겨진 패턴을 찾는 것이 분석가의 가장 큰 역할임을 깨달았습니다.

모델 성능을 높이기 위해선 데이터 전처리가 가장 중요합니다. 결측값 처리, 이상치 제거, 변수 정규화를 통해 데이터를 정제한 뒤 모델에 입력했을 때 성능이 확연히 좋아졌습니다.  
단순한 평균 대체나 IQR 방식의 이상치 제거가 **랜덤 포레스트 모델의 정확도를 10% 이상 향상**시키는 데 기여했습니다.  
"좋은 데이터가 좋은 모델을 만든다"는 말을 몸소 체험한 순간이었습니다.

Gradient Boosting 모델은 뛰어난 성능을 보여줬지만, 학습 시간이 길어 **실시간 적용에는 한계**가 있다는 점을 발견했습니다.  
이 과정에서 "모델 성능만큼 실용성도 중요하다"는 것을 깨달았고, 분석의 목적에 맞는 모델을 선택하는 것이 데이터 분석가의 중요한 역량임을 느꼈습니다.

---


## 출처
```
중소벤처기업부, Korea AI Manufacturing Platform(KAMP), 품질 이상탐지, 진단(크로메이트) AI 데이터셋, KAIST (주)에이비에이치, (주)임픽스), 2021.12.27., www.kamp-ai.kr
