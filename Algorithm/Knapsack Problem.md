# 배낭 문제(Knapsack Problem)

Knapsack Problem은 조합 최적화의 유명한 문제이다.

배낭 문제는 배낭에 담을 수 있는 무게의 최댓값은 정해져 있고, 일정 가치와 무게가 있는 짐들을 배낭에 넣을 때, 가치의 합이 최대가 되도록 짐을 고르는 방법을 찾는 문제이다.

## Knapsack Problem 종류
+ 분할가능 배낭문제(Fractional Knapsack Problem)
    + 짐을 쪼갤 수 있는 경우(무게가 소수일 수 있는 경우)
    + 그리디(Greedy) 알고리즘
    + 다항 시간으로 풀이 가능하다.
+ 0-1 배낭문제(0-1 Knapsack Problem)
짐을 쪼갤 수 없는 경우
    + 동적계획법(Dynamic Programming)
    + 단, NP-complete이기 때문에 알려진 다항 시간 알고리즘은 없다.
    + 보통 Knapsack Problem라고 하면 0-1 Knapsack Problem가 주로 다루어진다.

## 0-1 Knapsack Problem

### 방법1 - DP 2차원 배열
```python
import sys
input = sys.stdin.readline

n, k = map(int, input().split())
w, v = [0] * (n + 1), [0] * (n + 1)
for i in range(1, n + 1):
    w[i], v[i] = map(int, input().split())

dp = [[0] * (k + 1) for _ in range(n + 1)]
for i in range(1, n + 1):
    for j in range(1, k + 1):
        if j < w[i]:
            dp[i][j] = dp[i - 1][j]
        else:
            dp[i][j] = max(dp[i - 1][j], dp[i - 1][j - w[i]] + v[i])

print(dp[n][k])
```

### 방법 2 - DP 1차원 배열 (방법 1보다 실행시간 감소)
```python
import sys
input = sys.stdin.readline

n, k = map(int, input().split())
wv = [list(map(int, input().split())) for _ in range(n)]

wv.sort()
dp = [0] * (k + 1)
for w, v in wv:
    for i in range(k, w - 1, -1):
        dp[i] = max(dp[i - w] + v, dp[i])

print(dp[k])
```


<br>

관련 문제
+ [평범한 배낭](https://www.acmicpc.net/problem/12865)

참고
+ <https://ko.wikipedia.org/wiki/%EB%B0%B0%EB%82%AD_%EB%AC%B8%EC%A0%9C>
+ https://gsmesie692.tistory.com/113
+ https://aigong.tistory.com/389