# dict, Counter에서 최댓값 추출하기

## 1. dict

```python
answer = [k for k, v in dic if v == max(dic.values())]
```

## 2. Counter

```python
counter = Counter(arr).most_common()
answer = [k for k, v in counter if v == counter[0][1]]
```