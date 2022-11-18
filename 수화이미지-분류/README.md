# 수화 이미지 분류 경진대회

0부터 10까지 수화 이미지를 통해 숫자를 분류

대회 링크: https://dacon.io/competitions/official/235896/overview/description

코드 공유: https://dacon.io/competitions/official/235896/codeshare/5075?page=1&dtype=recent

## 수화 이미지 분류하면서 알게된 점

`1.` `torchvision.transforms` 대신에 `albumentations`을 사용하면 다양한 이미지 변형을 더 빠르게 할 수 있다

## Learning Rate

![](https://github.com/Jaesu26/Dacon-Basic/blob/main/%EC%88%98%ED%99%94%EC%9D%B4%EB%AF%B8%EC%A7%80-%EB%B6%84%EB%A5%98/learning_rate.png)

## Neural Network Architecture

`-` 내가 직접 네트워크를 설계하기 보단 기존에 있는 State-of-the-Art model을 사용하자
