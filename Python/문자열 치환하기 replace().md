# 문자열 치환하기 replace()

## replace
+ 문자열을 치환해주는 메서드
+ 문자열.replace('검색 문자', '치환 문자')
+ 문자열에서 '검색 문자'와 일치하는 문자를 모두 '치환 문자'로 변경한다.


## 사용 예시
```python
s = 'Hello World!'
s = s.replace('Hello', 'Hi,')

print(s)

# Output
Hi, World!
```

## 치환 횟수 설정
+ 문자열.replace('검색 문자', '치환 문자', 치환 횟수)
+ 치환 횟수를 지정하여 앞에서부터 원하는 개수만큼 변환할 수 있다.

```python
fruit = 'apple, banana, apple, orange'
fruit = fruit.replace('apple', 'grape', 1)

print(fruit)

# Output
grape, banana, apple, orange
```


<br>

참고
<https://ponyozzang.tistory.com/334>