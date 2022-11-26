# find(), index() 차이

## 공통점

find와 index 모두 특정 문자를 찾을 때 사용한다. 인자로 문자를 넘기면 해당 문자가 위치한 인덱스를 반환한다.

### 사용 예시 1

+ 문자열.find('찾을 문자')
+ 문자열.index('찾을 문자')

```python
s = 'Hello, world!'

print(s.find('o'))
print(s.index('o'))

# 출력
4
4
```

### 사용 예시 2

+ 문자열.find('찾을 문자', 시작 위치, 종료 위치)
+ 문자열.index('찾을 문자', 시작 위치, 종료 위치)

```python
s = 'Hello, world!'

print(s.find('o', 1, 7))
print(s.index('o', 7))  # 숫자가 1개인 경우 시작점을 나타낸다.

# 출력
4
8
```

## 차이점 1
+ find() - 찾는 문자가 없는 경우에 -1을 반환한다.
+ index() - 찾는 문자가 없는 경우에 ValueError가 발생한다.

## 차이점 2
+ find() - 문자열만 사용 가능하다.
+ index() - 문자열, 리스트, 튜플 자료형에서 사용 가능하다.


<br><br>
참고
<https://ooyoung.tistory.com/78>