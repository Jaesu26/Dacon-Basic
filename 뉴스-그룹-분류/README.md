# 뉴스 그룹 분류 경진대회

대회 링크: https://dacon.io/competitions/official/235884/overview/description

코드 공유 : https://dacon.io/competitions/official/235884/codeshare/4822?page=1&dtype=recent

## 뉴스 그룹 분류하면서 알게된 점

`1.` 단어에 값을 부여하는 방식 중 `Count Vectorizer`와 `TF-IDF Vectorizer`는 중요하니 알아두자

`2.` 파이토치의 `DataLoader` 클래스가 가지는 `collate_fn` 메소드를 통해 `Dataset`의 output을 어떻게 처리하여 return할 지 조작할 수 있다

`3.` 반복되는 연산은 함수로 만들어서 활용하자(다른 대회에서도 사용할 수 있게 하자) 
