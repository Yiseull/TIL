# input() 보다 빠른 sys.stdin.readline()

파이썬에서 input()을 통해 입력 받는 것보다 sys.stdin.readline()이 더 빠르다

## 사용 예시
```python
import sys
input = sys.stdin.readline

n, m = map(int, input().split())
arr = [input().strip() for _ in range(m)]
```