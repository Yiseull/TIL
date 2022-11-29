# collections.defaultdict

defaultdict()는 dict 클래스의 서브 클래스이다.

첫 번째 인자로 함수를 넘기면, 모든 키에 대해서 값이 없는 경우 인자로 넘어온 함수를 호출하여 그 결과값으로 지정한다. 즉 함수의 결과값이 딕셔너리의 초깃값으로 지정된다. 만약 인자가 없으면 KeyError 예외가 발생한다.

## defaultdict 사용 예시

### 1. defaultdict(int)

키에 대한 값을 지정하지 않은 경우, default_factory 함수는 인자로 넘긴 int()를 호출하여 값을 0으로 지정한다.

```python
from collections import defaultdict

dict_int = defaultdict(int)
print(dict_int['key'])

# 출력
0
```

### 2. defaultdict(list)

키에 대한 값을 지정하지 않은 경우, default_factory 함수는 인자로 넘긴 list()를 호출하여 값을 빈 list로 지정한다.

```python
from collections import defaultdict

dict_list = defaultdict(list)
print(dict_list['key'])

# 출력
[]
```

## default값을 0이 아닌 다른 값으로

항상 0을 반환하는 함수 int()는 상수 함수의 특별한 경우이다.

default값을 0 말고 다른 상숫값으로 설정하고 싶은 경우에는 lambda 함수를 사용하면 된다.

```python
from collections import defaultdict

dict1 = defaultdict(lambda:1)
dict2 = defaultdict(lambda:2)

print(dict1['key'], dict2['key'])

# 출력
1 2
```

<br><br>

참고
<https://dongdongfather.tistory.com/69>
<https://www.daleseo.com/python-collections-defaultdict/>
<https://docs.python.org/ko/3/library/collections.html#collections.defaultdict.default_factory>