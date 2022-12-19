# set copy() in python

"="를 사용하여 set을 복사하면 복사된 set에서 수정하면 원래 set에도 변경 사항이 반영됩니다. 따라서 copy() 메서드를 통해서 set을 복사해야 합니다.

+ copy() 사용법:
```python
set_name.copy()
```

+ Parameters: 매개변수는 사용하지 않습니다.

+ Return value: 원래 set의 복사본을 반환합니다.

+ 예제:
```python
set1 = {1, 2, 3}
set2 = set1.copy()
set2.add(5)

print(set1)
print(set2)

# Output
{1, 2, 3}
{1, 2, 3, 5} 
```

<br>

참고
<https://www.geeksforgeeks.org/set-copy-python/>