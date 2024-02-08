# 손동작 분류 경진대회

손에 부착된 센서의 데이터를 통해 총 4개의 종류의 손동작을 분류

대회 링크: https://dacon.io/competitions/official/235876/overview/description

## 손동작 분류하면서 알게된 점

`1.` 파이토치의 Conv2D에서 `padding="same"`은 stride가 1일 때만 가능하다

`2.` Early Stopping과 K-Fold Cross Validation을 통해 과적합을 피하고 일반화 성능을 향상시키자

## 대회 1등의 접근 방식

1등 코드 링크: https://dacon.io/competitions/official/235876/codeshare/4686?page=1&dtype=recent

**센서 번호가 4씩 떨어진 변수 사이에 상관관계가 있음을 EDA를 통해 알아냈다**

**이들을 하나의 변수로 묶어주기 위해 데이터를 (8, 4) 행렬로 만들어주고 CNN을 통해 피쳐를 추출해냈다**

나는 이를 고려하지 않고 피쳐간의 연관성이 존재할 것이라 생각해 CNN을 사용하고자 (4, 8) 행렬로 바꿔주었다 (무지성)
