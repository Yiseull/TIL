# 소수(Prime Number) 판별 알고리즘

```python
import math

def primeNumber(n: int) -> bool:
    for i in range(2, int(math.sqrt(n)) + 1):
        if n % i == 0:
            return False
    return True
```