# 올림 함수 ceil, 내림 함수 floor

ceil 함수와 floor 함수는 math 모듈에 속해있다.

## math.ceil(x)
ceil 함수는 인자로 들어온 실수 x의 올림 값을 반환한다. 반환 값은 정수 타입이다.

예제
```python
from math import ceil

print(ceil(2.56))
print(ceil(52.2))
print(ceil(-1.3))

# Output
3
53
-1
```


## math.floor(x)
floor 함수는 인자로 들어온 실수 x의 내림 값을 반환한다. 반환 값은 정수 타입이다.

예제
```python
from math import floor

print(floor(2.56))
print(floor(52.2))
print(floor(-1.3))

# Output
2
52
-2
```


<br>

참고
<https://ooyoung.tistory.com/99>