# sort()와 sorted()

파이썬에서 리스트를 정렬할 때 sort()와 sorted()를 사용하면 된다.

둘의 차이점은 기존의 리스트가 변경되는지 안되는지 그 차이다.

<br>

## list.sort()
+ 리스트형의 메서드
+ a.sort() 형식으로 사용
+ 리스트 자체를 직접 변경

```python
a = [5,2,3,4,1]
b = a.sort()
print(a)    # 출력: [1,2,3,4,5]
print(b) # 출력: None
```
주의*** sort() 함수의 리턴 값은 None

<br>

## 내장함수 sorted()
+ 파이썬의 표준 내장 함수
+ sorted(a) 형식으로 사용
+ 기존의 리스트를 변경하지 않고 정렬된 새로운 리스트를 반환

```python
a = [5,2,3,4,1]
b = sorted(a)
print(a)    # 출력: [5,2,3,4,1]
print(b) # 출력: [1,2,3,4,5]
```

sort()는 리스트만을 위한 함수지만 sorted()는 어떤 이터러블 객체든 정렬 가능하다.

```python
a = "dltmftil"
b = sorted(a)
print(a)    # 출력: dltmftil
print(b) # 출력: ['d','f','i','l','l','m','t','t']
```

<br>

## 내림차순 정렬
sort()와 sorted() 기본으로 오름차순 정렬이다. 내림차순으로 정렬하려면 reverse=True 이용하면 된다.

```python
a = [5,2,3,4,1]
sorted(a, reverse=True)
a.sort(reverse=True)

# 내림차순 정렬 후 [5,4,3,2,1]
```