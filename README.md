# IMBK Bank Customer Churn ML

## 1. 프로젝트명
고객 이탈 분류 ML 및 인사이트 분석

## 2. 기간
2026년 4월 10일

## 3. 기술 스택
- Python
- Pandas, Numpy
- Seaborn
- Scikit-learn
- LightGBM
- AdaBoost
- Gradient Boositng
- RandomForest
- Optuna
- SHAP

## 4. 데이터 출처
- Kaggle Bank Customer Churn Dataset  
- row: 10000 / col: 12

---

## 5. 데이터 전처리
- 결측치 확인
- customer_id 제거 (단순 식별자)
- country, gender Label Encoding (범주형 변수 인코딩)
- 데이터 분할 (train / valid, stratify 적용)

---

## 6. EDA 및 해석
- 고객 이탈 여부 분포확인
- churn 비율 약 20% → 클래스 불균형 존재
- Female 고객의 churn 비율이 더 높음
- Germany 지역 churn 비율이 높게 나타남
- 시각화를 통해 이탈 고객 특성 해석

👉 따라서 Accuracy보다 F1-score를 주요 평가 지표로 사용

---

## 7. 모델링 과정

### 1) AutoML (PyCaret)

<img width="625" height="269" alt="auto" src="https://github.com/user-attachments/assets/08fcd7d2-6fd9-4b4f-8606-114853c2f337" />

상위 모델 선정
- AdaBoost
- LightGBM
- GradientBoosting
- RandomForest

### 2) Hyperparameter Tuning (Optuna)

<img width="173" height="63" alt="Hyperparameter Tuning" src="https://github.com/user-attachments/assets/85881f42-dc01-47aa-baee-b54777b25c2d" />

각 모델별 최적 파라미터 탐색

### 3) 최종 모델
- GradientBoostingClassifier
- F1-score ≈ 0.603

### 4) Stacking Model

- 성능 출력
  
<img width="201" height="35" alt="Stacking Pipe" src="https://github.com/user-attachments/assets/d1eef43d-cb00-4fcd-818a-634ba13a95f2" />

- F1-score ≈ 0.602
- Accuracy ≈ 0.868

👉 단일 모델과 유사한 성능

---

## 8. 인사이트 제안 - SHAP Value 해석

<img width="629" height="439" alt=" Shap value" src="https://github.com/user-attachments/assets/1f8444e8-a244-4cb2-82de-37753dcc4d69" />

- active_member가 높은 고객은 churn 확률이 낮음 → 핵심 유지 대상
- 일부 고객군에서 age, products_number가 churn에 영향
- 활동성이 낮은 고객을 중심으로 관리 전략 필요

👉 타겟 마케팅 및 고객 유지 전략 수립 가능

---

## 9. Reference
- Kaggle Dataset
- Scikit-learn Documentation
- SHAP Documentation




