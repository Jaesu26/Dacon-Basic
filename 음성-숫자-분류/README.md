# 음성 분류 경진대회

0~9까지 숫자를 말하는 음성 데이터를 이용해 숫자를 분류

대회 링크: https://dacon.io/competitions/official/235905/overview/description

## 음성 분류하면서 알게된 점

`1.` 푸리에 변환을 통해 음성 데이터를 주기함수들의 합으로 분해하여 특징을 추출할 수 있다

`2.` 단순히 푸리에 변환을 하여 음성 데이터의 특징을 추출하기보단 MFCC와 Mel Spectrogram을 사용하여 특징을 추출하는 것이 더 효과적이다

`3.` 푸리에 변환을 공부하자...
