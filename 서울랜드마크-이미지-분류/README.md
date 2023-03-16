# 서울 랜드마크 이미지 분류 경진대회

서울 랜드마크 이미지 데이터 셋을 이용하여 랜드마크의 이름을 대표하는 라벨을 분류

대회 링크: https://dacon.io/competitions/official/235957/overview/description

코드 공유: https://dacon.io/competitions/official/235957/codeshare/6481

## 서울 랜드마크 이미지 분류하면서 알게된 점

`1.` 이미지 변형을 통해 데이터를 증강할 땐 꼭 변형된 이미지를 확인해야 한다!

`2.` 예시로 `albumentations` 패키지에 있는 [`GaussNoise`](https://github.com/albumentations-team/albumentations/blob/1.2.1/albumentations/augmentations/transforms.py#L1789) 클래스는 이미지 변형 후 이를 반환할 때 픽셀값을 0과 1사이로 만드므로 픽셀값을 미리 정규화해야 한다
