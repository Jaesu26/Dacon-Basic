# 쇼핑몰 리뷰 평점 분류 경진대회

쇼핑몰 리뷰의 평점(1, 2, 4, 5)을 분류하는 모델을 만들자

## BERT 모델

LinearSVC, RNN과 같은 모델보다 Transformer 모델의 성능이 더 우수하다

- Transformer 모델에 따른 성능

kfold training을 할 땐 조기중단을 사용

scheduler는 transformers의 get_cosine_schedule_with_warmup를 사용 (warmup_step은 전체의 0.1)

preprocessing은 텍스트를 정제하고 띄어쓰기를 교정 (텍스트 정제: https://github.com/Beomi/KcELECTRA, 띄어쓰기: `pykospacing` 패키지 사용)

|model name|preprocessing|epochs|batch size|learning rate|max len|label smoothing|scheduler|valid acc|public acc|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|skt/kobert-base-v1|False|2|64|5e-5|64|0.05|O|0.68631|0.68344|
|klue/roberta-base|False|2|64|1e-5|50|0.05|X|0.7054|0.68952|
|klue/roberta-base|False|5 fold|128|1e-5|50|0.05|X|0.6958|0.69568|
|kykim/electra-kor-base|False|5 fold|64|1e-5|50|0.05|X|0.7040|0.7064|
|kykim/electra-kor-base|True (Space X)|5 fold|128|1e-5|50|0.05|O|0.7072|0.70512|
|kykim/electra-kor-base|True|5 fold|128|2e-5|50|0.0|O|0.7028|0.7060|
|kykim/electra-kor-base|False|5 fold|128|2e-5|50|0.05|X|0.7033|0.70872|
|kykim/electra-kor-base|True|5 fold|128|2e-5|50|0.05|O|0.7078|0.70664|
|kykim/electra-kor-base|False|5 fold|128|2e-5|50|0.1|X|0.7033|0.70544|
|kykim/electra-kor-base|False|5 fold|256|3e-5|50|0.05|O|0.7048|0.7048|
|kykim/electra-kor-base|False|10 fold|128|2e-5|50|0.05|O|0.7064|0.70496|
|kykim/funnel-kor-base|False|5 fold|128|1e-5|50|0.05|X|0.7017|0.7024|
|kykim/funnel-kor-base|True|5 fold|128|1e-5|50|0.05|O|0.7070|0.70536|
|monologg/koelectra-base-v3-discriminator|False|5 fold|128|2e-5|50|0.05|O|0.6953|0.69432|
