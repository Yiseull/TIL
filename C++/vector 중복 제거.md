# vector에서 중복 원소를 제거하는 법

벡터에서 중복 원소를 제거할 때, sort(), unique(), erase()를 사용해서 제거할 수 있습니다.

1. sort(): 벡터를 정렬한다.
2. unique(): 중복 원소를 vetor의 제일 뒷부분(쓰레기 값)으로 보내고, 쓰레기 값의 첫 번째 위치를 반환한다.
3. erase(): 인자로 넣은 범위의 속하는 모든 값을 삭제한다.

<br>

사용 예시
```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() 
{
    vector<int> v;
    v.push_back(1);
    v.push_back(3);
    v.push_back(2);
    v.push_back(1);
    v.push_back(2);
    v.push_back(4);

    sort(v.begin(), v.end());
    v.erase(unique(v.begin(), v.end()), v.end());
}

```
** sort와 unique를 사용하기 위해선 algorithm 라이브러리를 include 필요

<br><br>

참고
<https://dpdpwl.tistory.com/39>
<https://dar0m.tistory.com/77>