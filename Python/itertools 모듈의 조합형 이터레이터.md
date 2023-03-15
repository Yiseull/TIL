# itertools 모듈의 조합형 이터레이터

이 모듈은 자체적으로 혹은 조합하여 유용한 빠르고 메모리 효율적인 도구의 핵심 집합을 표준화합니다. 

## 조합형 이터레이터

### 1. product()
+ product(*iterables, [repeat=1])
+ 데카르트 곱(cartiesian product)
+ 중첩된 for 루프와 동등. 예를 들어, product(A, B)는 ((x,y) for x in A for y in B)와 같은 것을 반환
+ 이터러블의 자신과의 곱을 계산하려면, 선택적 repeat 키워드 인자를 사용하여 반복 횟수를 지정. 예를 들어, product(A, repeat=4)는 product(A, A, A, A)와 같은 것을 뜻함

```python
product('ABCD', repeat=2) # AA AB AC AD BA BB BC BD CA CB CC CD DA DB DC DD
product('ABCD', 'xy') # Ax Ay Bx By Cx Cy Dx Dy
product(range(2), repeat=3) # 000 001 010 011 100 101 110 111
```

### 2. permutations()
+ permutations(iterable, r=None)
+ r-길이 튜플들, 모든 가능한 순서, 반복되는 요소 없음
+ r이 지정되지 않았거나 None이면, r의 기본값은 iterable의 길이이며 가능한 모든 최대 길이 순열이 생성

```python
permutations('ABCD', 2) # AB AC AD BA BC BD CA CB CD DA DB DC
permutations(range(3)) # 012 021 102 120 201 210
```

### 3. combinations()
+ combinations(iterable, r)
+ r-길이 튜플들, 정렬된 순서, 반복되는 요소 없음

```python
combinations('ABCD', 2) # AAB AC AD BC BD CD
combinations(range(4), 3) # 012 013 023 123
```

### 4. combinations_with_replacement()
+ combinations_with_replacement(iterable, r)
+ r-길이 튜플들, 정렬된 순서, 반복되는 요소 있음
+ 요소는 값이 아니라 위치로 고유성을 다룸. 따라서 입력 요소가 고유하면, 생성된 조합도 고유

```python
combinations_with_replacement('ABCD', 2) # AA AB AC AD BB BC BD CC CD DD
```

<br>

Reference

<https://docs.python.org/ko/3/library/itertools.html#itertools.combinations>