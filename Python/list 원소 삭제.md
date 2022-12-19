# list 원소 삭제 - del, remove, pop, clear

### 1. del 키워드를 통한 삭제

+ del list_name[index]
+ 특정 위치의 요소를 삭제한다.
+ 특정 범위의 요소들도 삭제 가능하다.

```python
a = [1, 2, 3, 4, 5]
del a[2]

b = [1, 2, 3, 4, 5]
del b[2:4]  # 2~3까지 삭제됨

print(a)
print(b)

# Output
[1, 2, 4, 5]
[1, 2, 5]
```

### 2. remove()에 의한 삭제

+ list_name.remove(삭제할 원소)
+ 삭제할 원소가 없으면 ValueError가 발생한다.
+ 리스트에 같은 값이 여러 개 있는 경우, 첫 번째 값이 삭제된다.

```python
a= [1, 2, 3, 4, 5]
a.remove(4)

print(a)

# Output
[1, 2, 3, 5]
```

### 3. pop() 맨 뒤의 값 삭제

+ 리스트의 마지막 원소를 삭제하고, 해당 값을 반환한다.
+ 인자로 index를 지정하여 지정한 index 위치의 값을 삭제하는 것도 가능하다.

```python
a = [1, 2, 3, 4, 5]

print(a.pop())

# Output
5
```

### 4. clear() 모든 원소 삭제

+ list_name.clear()
+ 리스트의 모든 원소가 삭제되고 빈 리스트만 남는다.

```python
a = [1, 2, 3, 4, 5]
a.clear()

print(a)

# Output
[]
```

<br>

참고
<https://wikidocs.net/16040>