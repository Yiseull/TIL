# 숫자형 리스트 Unpacking

### 방법 1 - map을 통해 str로 변환

```python
my_list = [2, 5, 1, 6]
print(' '.join(map(str, my_list)))

# Output
2 5 1 6
```

### 방법 2 - Asterisk(*) 사용
```python
my_list = [2, 5, 1, 6]
print(*my_list)

# Output
2 5 1 6
```

시간을 측정해보니 방법 1이 더 빠른 듯 하다!