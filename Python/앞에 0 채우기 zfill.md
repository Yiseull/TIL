# 앞을 0으로 채우기 zfill()

앞에 0을 채우고 싶은 경우, zfill() 메서드를 사용한다.


## str.zfill(width)
+ zfill() 메서드는 문자열이 특정 길이가 되도록 문자열 앞을 '0'으로 채워준다.
+ zfill() 메서드는 문자열 메서드이다. 따라서 숫자 앞에 0을 채우려면 문자열로 형변환 후 zfill() 메서드를 사용해야 한다.


### 예제 1
```python
a = 5
print(str(a).zfill(3))
print(str(a).zfill(5))

# Output
003
00005
```

### 예제 2
```python
b = 'cc'
print(b.zfill(3))

# Output
0cc
```