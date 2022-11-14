# for문 거꾸로 반복하기

5부터 1까지 역순으로 출력

```python
for i in range(5, 0, -1):
    print(i)

# 출력
5
4
3
2
1
```

<br>

### 다른 방법 - reversed() 이용

```python
for i in reversed(range(5)):
    print(i + 1)

# 출력
5
4
3
2
1
```