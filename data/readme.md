# 데이터 설명

이 디렉토리에는 스마트 팩토리 크로메이트 공정 데이터 분석 프로젝트에 사용된 데이터 파일이 포함되어 있습니다.  
데이터는 KAMP(Korea AI Manufacturing Platform)에서 제공하며, 공정 데이터를 기반으로 품질 이상 탐지 및 진단에 활용됩니다.

---

## 파일 목록
1. **`raw_data.csv`**  
   - 원본 데이터 파일입니다.  
   - 주요 컬럼:  
     - `Temperature`: 공정 과정의 온도 (°C)  
     - `pH`: 화학 용액의 산도 (0~14)  
     - `Pressure`: 공정 중 발생한 압력 (kPa)  
     - `QualityOutput`: 품질 상태 (정상/이상)

2. **`processed_data.csv`**  
   - 전처리가 완료된 데이터 파일입니다.  
   - 결측값 처리 및 이상치 제거 후, 정규화된 데이터가 포함되어 있습니다.

---

## 데이터 사용 방법
1. **원본 데이터**: 분석 전 데이터 전처리 단계에서 사용됩니다.  
   - 파일 경로: `./data/raw_data.csv`

2. **전처리 데이터**: 모델 학습 및 평가에 바로 사용할 수 있습니다.  
   - 파일 경로: `./data/processed_data.csv`

---

## 주의 사항
- 데이터는 프로젝트 목적에 따라 가공 및 변형되었습니다.  
- 원본 데이터는 개인 정보 보호와 데이터 사용 정책에 따라 외부 공유에 제한이 있을 수 있습니다.