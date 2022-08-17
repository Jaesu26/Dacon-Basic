# Dacon-Basic
데이콘 베이직 대회 참가하기

## 뗑컨 몸무게 예측하면서 알게된 점 

`1.` 코드를 제출하면 자동적으로 가장 우수한 점수를 가진 제출이 최종 제출로 변경된다(중요) ---> 확인를 못했음...

`2.` 종속 변수가 정규분포가 아닌 경우 로그 변환등을 통해 정규분포로 만들어 주는 것이 예측 능력에서 우수할 수 있다(잔차 그림을 그려봤을 때 딱히 문제가 없어보여서 이를 고려하지 않았음)

`3.` `lasso = Lasso(alpha=0.1)` ---> Lasso 클래스의 인스턴스를 생성하는 것, 또한 `lasso.fit`는 Lasso 클래스의 fit 메소드를 사용한 것

`4.` 표본이 적은 상황에서 모델을 평가하기 좋은 방법은 교차검증 ---> 한 쌍의 train, valid로 나누는 것보다 모델 성능을 측정함에 있어 더 낫다

`5.` train, valid의 RMSE를 plot에 그려봤을 때 둘의 차이가 크다면 일반화 성능이 좋지 않을 수 있음(valid의 RMSE는 작으면서 둘의 RMSE 차이를 크지 않게 하는 하이퍼 파라미터를 고르것이 중요)

`6.` 결측치(NA) 다루기 ---> `df.isnull().values.any()` : df에 NA가 하나라도 있으면 True, `df.fillna(x)` : df의 결측치를 x로 채운다

## 영화 감성 분류하면서 알게된 점 

`1.` NLP는 어렵다

`2.` 정규표현식은 매우 유용하다

## 집값 예측하면서 알게된 점 

`-` 코드 공유 : https://dacon.io/competitions/official/235869/codeshare/4428?page=1&dtype=recent

`1.` 나는 정리를 잘 못한다 ---> 1개의 csv파일을 만드는데 사용된 코드를 커밋하여 기록하기(한번에 몽땅 하려고 하지 말고)

`2.` train과 test에 같은 코드를 적용하는 경우가 많은데 이를 함수로 만들자(또한 사이킷런 pipeline 알아보기)

`3.` public score와 private score 차이가 많이 난다(public score 말고 valid score를 최종 제출 기준으로 삼는 것도 나쁘지 않음)  

## 항공사 고객 만족도 예측하면서 알게된 점

`1.` 다중공선성을 고려하여 변수를 선택하자

`2.` EDA는 필수!

## 손글씨(숫자) 분류하면서 알게된 점(연습)

`1.` 미니배치 사이즈가 너무 크면 메모리가 터져서 컴퓨터가 멈춘다

`2.` class에 대해 잘 알고있어야 사용자 정의 class를 만들기 쉽다(class 공부 필수!)

## 사물 이미지 분류하면서 알게된 점

`1.` test data에서 이미지 파일을 불러올 때 번호 순서대로 불러와야 올바르게 제출 파일을 만들 수 있다

## 손동작 분류하면서 알게된 점

`1.` 파이토치의 Conv2D에서 `padding='same'`은 stride가 1일 때만 가능하다

`2.` Early Stopping과 K-Fold Cross Validation을 통해 과적합을 피하고 일반화 성능을 향상시키자

## 전복 나이 예측하면서 알게된 점

`1.` 소수의 클래스에 대해 오버샘플링을 적용함으로써 성능 향상을 이끌어 낼 수 있다

`2.` 파생변수를 다양하게 생성하자

## 뉴스 그룹 분류하면서 알게된 점

`-` 코드 공유 : https://dacon.io/competitions/official/235884/codeshare/4822?page=1&dtype=recent

`1.` 단어에 값을 부여하는 방식 중 `Count Vectorizer`와 `TF-IDF Vectorizer`는 중요하니 알아두자

`2.` 파이토치의 `DataLoader` 클래스가 가지는 `collate_fn` 메소드를 통해 `Dataset`의 output을 어떻게 처리하여 return할 지 조작할 수 있다

`3.` 반복되는 연산은 함수로 만들어서 활용하자(다른 대회에서도 사용할 수 있게 하자) 

## 인구 소득 예측하면서 알게된 점

`1.` `optuna`를 사용하면 하이퍼 파라미터 튜닝을 간편하게 할 수 있다

`2.` 오버샘플링을 적용할 때 단순 복제가 아닌 `SMOTE`를 사용하여 과적합을 피하자

## 소비자 소비 예측하면서 알게된 점

`1.` 모델 앙상블을 통해 예측값의 분산을 감소시키자

`2.` NMAE 평가 지표는 실제로 작은 값보다 실제로 큰 값을 잘 맞춰야 유리하다

## 수화 이미지 분류하면서 알게된 점

`-` 코드 공유 : https://dacon.io/competitions/official/235896/codeshare/5075?page=1&dtype=recent

`1.` `torchvision.transforms` 대신에 `albumentations`을 사용하면 다양한 이미지 변형을 더 빠르게 할 수 있다

`2.` 라벨 스무딩을 통해 과적합을 피할 수 있다

`3.` Test Time Augmentation(TTA)를 사용하여 앙상블과 같은 효과를 낼 수 있다

## 음성 분류하면서 알게된 점

`1.` 푸리에 변환을 통해 음성 데이터를 주기함수들의 합으로 분해하여 특징을 추출할 수 있다

`2.` 단순히 푸리에 변환을 하여 음성 데이터의 특징을 추출하기보단 MFCC와 Mel Spectrogram을 사용하여 특징을 추출하는 것이 더 효과적이다

`3.` 푸리에 변환을 공부하자...

## 쇼핑몰 리뷰 평점 분류하면서 알게된 점

`-` 코드 공유 : https://dacon.io/competitions/official/235938/codeshare/5938?page=1&dtype=recent

`1.` Transformer는 자연어 처리 분야에서 매우 우수한 모델이다

`2.` `transformers` 패키지의 Auto Classes를 활용해 손쉽게 트랜스포머 모델을 불러올 수 있다

`3.` Auto Classes : https://huggingface.co/docs/transformers/model_doc/auto
