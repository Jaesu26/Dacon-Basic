# 쇼핑몰 리뷰 평점 분류 경진대회

쇼핑몰 리뷰의 평점(1, 2, 4, 5)을 분류하는 모델을 개발

`-` 코드 공유 : https://dacon.io/competitions/official/235938/codeshare/5938?page=1&dtype=recent

## 쇼핑몰 리뷰 평점 분류하면서 알게된 점

`1.` Transformer는 자연어 처리 분야에서 매우 우수한 모델이다

`2.` `transformers` 패키지의 Auto Classes를 활용해 손쉽게 트랜스포머 모델을 불러올 수 있다

`3.` Auto Classes : https://huggingface.co/docs/transformers/model_doc/auto

## Transformer 모델

`-` LinearSVC, RNN과 같은 모델보다 Transformer 모델의 성능이 더 우수하다

- Transformer 모델에 따른 성능

`-` Kfold training을 할 땐 조기중단을 사용 (patience는 1로 설정)

`-` scheduler는 transformers의 get_cosine_schedule_with_warmup를 사용 (warmup_step은 전체의 0.1)

`-` preprocessing은 텍스트를 정제하고 띄어쓰기를 교정 (텍스트 정제: https://github.com/Beomi/KcELECTRA, 띄어쓰기: `pykospacing` 패키지)

`-` 모델을 여러개 사용한 경우 예측값을 평균내어 앙상블 (파라미터는 동일한 경우 한 번만 적었으며 다른 경우 콤마로 구분, 각 모델을 따로 학습시킨 후 앙상블하여 예측했기에 valid acc와 public acc가 상이하여 valid acc는 기입하지 않음)

`-` 표기하지 않은 파라미터(i.g. dropout)의 경우 모델의 기본값을 사용

|model name|preprocessing|epochs|batch size|learning rate|max len|label smoothing|scheduler|valid acc|public acc|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|skt/kobert-base-v1|False|2|64|5e-5|64|0.05|O|0.68631|0.68344|
|klue/roberta-base|False|2|64|1e-5|50|0.05|X|0.7054|0.68952|
|klue/roberta-base|False|5 fold|128|1e-5|50|0.05|X|0.6958|0.69568|
|monologg/koelectra-base-v3-discriminator|False|5 fold|128|2e-5|50|0.05|O|0.6953|0.69432|
|kykim/electra-kor-base|False|5 fold|64|1e-5|50|0.05|X|0.7040|0.7064|
|kykim/electra-kor-base|False|5 fold|128|2e-5|50|0.05|X|0.7033|0.70872|
|kykim/electra-kor-base|False|5 fold|128|2e-5|50|0.1|X|0.7033|0.70544|
|kykim/electra-kor-base|False|5 fold|256|3e-5|50|0.05|O|0.7048|0.7048|
|kykim/electra-kor-base|False|10 fold|128|2e-5|50|0.05|O|0.7064|0.70496|
|kykim/electra-kor-base|True (Space X)|5 fold|128|1e-5|50|0.05|O|0.7072|0.70512|
|kykim/electra-kor-base|True (Space X)|5 fold|128|2e-5|50|0.05|O|0.7050|0.7080|
|kykim/electra-kor-base|True|5 fold|128|2e-5|50|0.0|O|0.7028|0.7060|
|kykim/electra-kor-base|True|5 fold|128|2e-5|50|0.025|O|0.7046|0.70632|
|kykim/electra-kor-base|True|5 fold|128|2e-5|50|0.05|O|0.7066|0.7076|
|kykim/electra-kor-base|True|5 fold|128|2e-5|50|0.075|O|0.7044|0.70672|
|kykim/funnel-kor-base|False|5 fold|128|1e-5|50|0.05|X|0.7017|0.7024|
|kykim/funnel-kor-base|True (Space X)|5 fold|128|2e-5|50|0.05|O|0.7064|0.70616|
|kykim/funnel-kor-base|True|5 fold|128|1e-5|50|0.05|O|0.7070|0.70536|
|kykim/funnel-kor-base|True|5 fold|128|2e-5|50|0.05|O|0.7053|0.71216|
|kykim/electra-kor-base, kykim/funnel-kor-base|True (Space X)|5 fold|128|2e-5|50|0.05|O| |0.70944|
|kykim/electra-kor-base, kykim/funnel-kor-base|True|5 fold|128|2e-5|50|0.05|O| |0.7124|
