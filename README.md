# 🏦 Santander 고객 만족도 예측 모델

### 1. 프로젝트 소개
Kaggle의 Santander 은행데이터를 사용해 고객 만족 여부를 예측하는 최적의 모델을 개발하는 프로그램입니다.

### 2. 사용데이터 
데이터 출처 : https://www.kaggle.com/competitions/santander-customer-satisfaction/overview 

### 3. 주요 기능
- 데이터 전처리
  특수값(-999999) 최빈값으로 변경, 중복 변수 제거, 피처 스케일링을 적용했습니다
- 4가지 모델
  Logistic Regression, Decision Tree, RandomForest, XGBoost를 사용해 성능을 비교하였습니다<br>
| 모델         | 최적 하이퍼파라미터              | 교차 검증 AUC (Tuned) |<br>
| 로지스틱 회귀 | `{'C': 0.72, 'penalty': 'l2'}` | 0.7911 |<br>
| 결정 트리 | `{'max_depth': 6, 'min_samples_leaf': 8, 'min_samples_split': 9}` | 0.8092 |<br>
| 랜덤 포레스트 | `{'n_estimators': 100, 'max_depth': 15, 'min_samples_leaf': 7, ...}` | 0.8156 |<br>
| **XGBoost** | `{'subsample': 0.7, 'n_estimators': 50, 'max_depth': 4, ...}` | **0.8345** |

### 4. 결과 
  최종 선택 모델 : XGBoost
  4가지 모델 중 3가지의 모델의 AUC값이 큰 차이가 나지 않아 RandomizedSearchCV를 이용해 CrossValidation 결과, 약 0.835를 달성하며 XGBoost가 최적 모델임을 확인했습니다.

### 5. 사용기술

<p align="left">

<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />

<img src = "https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" />

<img src = "https://img.shields.io/badge/XGBoost-0063A1?style=for-the-badge&logo=xgboost&logoColor=white" />
</p>
