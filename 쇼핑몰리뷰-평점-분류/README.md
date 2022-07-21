# 쇼핑몰 리뷰 평점 분류 경진대회

쇼핑몰 리뷰의 평점(1, 2, 4, 5)을 분류하는 모델을 만들자

## BERT 모델

LinearSVC, RNN과 같은 모델보다 BERT 모델의 성능이 더 우수하다

- BERT 모델에 따른 성능

kfold training을 할 땐 조기중단을 사용

|model name|epochs|batch size|learning rate|max len|label smoothing|valid acc|public acc|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|skt/kobert-base-v1|2|64|5e-5|64|0.05|0.68631|0.68344|
|klue/roberta-base|2|64|1e-5|50|0.05|0.7054|0.68952|
|klue/roberta-base|5 fold|128|1e-5|50|0.05|0.6958|0.69568|
