# input() 보다 빠른 sys.stdin.readline()

파이썬에서 input()을 통해 입력 받는 것보다 sys.stdin.readline()이 더 빠르다.

## 사용 예시
```python
import sys
input = sys.stdin.readline

n, m = map(int, input().split())
words = [input().strip() for _ in range(n)]
```

### 주의사항!
만약 strip()을 안하면 단어 끝에 '\n'이 붙어서 저장된다.

```python
import sys
input = sys.stdin.readline

words = [input() for _ in range(3)]

print(words)

# 입력
Hello
Iam
YISEUL

# 출력
['Hello\n', 'Iam\n', 'YISEUL\n']
```