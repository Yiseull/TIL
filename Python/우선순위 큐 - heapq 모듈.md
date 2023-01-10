# 우선순위 큐 - heapq 모듈 사용

## 자료구조 힙(heap)

### 힙(heap)이란?

+ 완전이진트리를 기본으로 한 자료구조이다.
+ 힙은 최댓값 및 최솟값을 찾아내는 연산을 빠르게 하기 위해 고안되었다.
+ 즉, 우선순위 큐를 위하여 만들어진 자료구조이다.
+ 힙 트리에서는 중복 값을 허용한다. (이진 탐색 트리에서는 허용 안함)

### 힙(heap) 종류

+ 최대 힙(max heap)
    + 부모노드의 키값이 자식노드의 키값보다 항상 큰 힙
    + key(부모 노드) >= key(자식 노드)
+ 최소 힙(min heap)
    + 부모노드의 키값이 자식노드의 키값보다 항상 작은 힙
    + key(부모 노드) <= key(자식 노드)


## heapq 모듈

heapq 모듈은 최소 힙 자료구조를 제공한다. 그리고 Python에서는 힙을 구현할 때 리스트를 사용한다.

+ 삽입: heappush(list_name, 넣을 원소)
+ 삭제: heappop(list_name)
+ 리스트를 힙으로 재구성: heapify(list_name)

### 연산 시간복잡도
+ heappush: O(nlogn)
+ heappop: O(nlogn)
+ heapify: O(n)

### heappush, heappop 예제
```python
from heapq import *

heap = []

heappush(heap, 3)   # 삽입
heappush(heap, 5)   # 삽입
heappush(heap, 1)   # 삽입
print(heappop(heap))    # 삭제
print(heappop(heap))    # 삭제

# Output
1
3
```

### heapify 예졔
```python
from heapq import *

heap = [7, 4, 1, 5, 6, 2]
heapify(heap)
print(heappop(heap))    # 삭제
print(heappop(heap))    # 삭제

# Output
1
2
```

## 최대 힙 사용하기
최소 힙이 아닌 최대 힙으로 사용하고 싶은 경우 원소를 삽입/삭제하는 경우 -1을 곱하면 된다.


```python
from heapq import *

heap = []

heappush(heap, -3)
heappush(heap, -5)
heappush(heap, -1)
print(-heappop(heap))
print(-heappop(heap))

# Output
5
3
```

<br>

참고

<https://www.daleseo.com/python-heapq/>
<https://seongonion.tistory.com/m/91>