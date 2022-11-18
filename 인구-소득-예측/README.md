# 인구 데이터 기반 소득 예측 경진대회

인구 데이터 바탕으로 소득이 5만달러 이하인지 초과인지 분류

대회 링크: https://dacon.io/competitions/official/235892/overview/description

## 인구 소득 예측하면서 알게된 점

`1.` `optuna`를 사용하면 하이퍼 파라미터 튜닝을 간편하게 할 수 있다

`2.` 오버샘플링을 적용할 때 단순 복제가 아닌 `SMOTE`를 사용하여 과적합을 피하자
