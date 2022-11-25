# collections.Counter

collections 모듈의 Counter 클래스에 대해서 정리했습니다.

Counter는 dict의 서브 클래스로, 요소가 딕셔너리 키로 저장되고 개수가 딕셔너리값으로 저장되는 컬렉션입니다. 따라서 dict 에서 제공하는 API를 그대로 사용 가능합니다.

```python
from collections import Counter

# 요소는 iterable
l = [1, 1, 2, 3, 4, 4]
s = 'helllloo'

print(Counter(l))
print(Counter(s))

# 출력 - 개수가 큰 순서대로 출력함
Counter({1: 3, 4: 2, 2: 1, 3: 1})
Counter({'l': 4, 'o': 2, 'h': 1, 'e': 1})
```

<br>

실제로는 딕셔너리를 한 번 더 래핑한 collections.Counter 클래스를 갖습니다.

```python
type(b)

# 출력
<class 'collections.Counter'>
```

<br>

## elements()

개수만큼 반복되는 요소에 대한 이터레이터를 반환합니다. 요소는 처음 발견되는 순서대로 반환됩니다.

<br>

## most_common([n])

Counter 객체에서 n개의 가장 빈도 수가 높은 것부터 가장 적은 것 순으로 나열한 리스트를 반환합니다. n이 생략되거나 None이면, 모든 요소를 반환합니다.


```python
l = [1, 1, 2, 3, 4, 4, 1]
counter = Counter(l)

print(counter.most_common())
print(counter.most_common(1))
print(counter.most_common(2))

# 출력
[(1, 3), (4, 2), (2, 1), (3, 1)]
[(1, 3)]
[(1, 3), (4, 2)]
```

<br>

## total()

개수의 합을 계산합니다.

(버전 3.10에 추가)

<br><br>
참고 
<https://docs.python.org/ko/3/library/collections.html#collections.Counter>