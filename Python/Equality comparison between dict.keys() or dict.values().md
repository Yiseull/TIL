# Equality comparison between dict.keys() or dict.values()

## keys()
Return a new view of the dictionary’s keys.

밑에 코드와 같이 keys()이 같으면 True를 반환하는 것 같다.

```python
dict1 = {'a': 1, 'b': 3}
dict2 = {'b': 3, 'a': 1}

print(dict1.keys() == dict2.keys())

# 출력 결과
True
```

## values()
Return a new view of the dictionary’s values.

An equality comparison between one dict.values() view and another will always return False. This also applies when comparing dict.values() to itself.

dict.values() 뷰 간의 동등성 비교는 항상 False를 반환한다.

```python
dict1 = {'a': 1, 'b': 3}
dict2 = {'b': 3, 'a': 1}

print(dict1.values() == dict2.values())

# 출력 결과
False
```

이는 자신과 비교할 때도 적용된다.

```python
myDict = {'a': 1}

print(myDict.values() == myDict.values())

# 출력 결과
False
```

<br><br>

참고
<https://docs.python.org/3.7/library/stdtypes.html?highlight=dict%20keys#dict.values>