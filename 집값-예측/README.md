# 집값 예측 경진대회

housing 데이터를 통한 집값 예측

대회 링크: https://dacon.io/competitions/official/235869/overview/description

코드 공유 : https://dacon.io/competitions/official/235869/codeshare/4428?page=1&dtype=recent

## 집값 예측하면서 알게된 점 

`1.` 나는 정리를 잘 못한다 ---> 1개의 csv파일을 만드는데 사용된 코드를 커밋하여 기록하기(한번에 몽땅 하려고 하지 말고)

`2.` train과 test에 같은 코드를 적용하는 경우가 많은데 이를 함수로 만들자(또한 사이킷런 pipeline 알아보기)

`3.` public score와 private score 차이가 많이 난다(public score 말고 valid score를 최종 제출 기준으로 삼는 것도 나쁘지 않음)  
