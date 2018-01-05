Marc's Cakewalk
===
[Q](https://www.hackerrank.com/challenges/marcs-cakewalk/problem)  


문제요약
---
마크는 컵케익을 좋아한다. 동시에 몸무게를 유지하고 싶어한다.
컵케익은 각각 Ci의 칼로리를 갖는다. 마크가 몸무게를 유지하기 위해서는 각각의 컵케익에 대해 Ci * (2^j) 마일만큼 걸어야한다.
이 때 마크가 걸어야하는 최소의 마일값을 구하라.

ex) 3개의 컵케익 섭취, 각각의 칼로리는 1, 3, 2칼로리이다.
C1 = 0 + (3 * (2^0)) = 3
C2 = 3 + (2 * (2^1)) = 7
C3 = 7 + (2 * (2^2)) = 11
따라서 최소 11마일을 걸어야한다.


문제분석
---
섭취한 컵 케익의 수(j)가 증가할 수록 Ci * (2^j)값이 증가하므로 최소 마일값을 구하기 위해서는 칼로리 리스트를 내림차순으로 정렬한 후 마일값을 계산해야 한다.

리스트를 역으로 정렬
-> list_name.sort(reverse = True)

소스코드
---
```python
#!/bin/python3

import sys

def marcsCakewalk(calorie):
    calorie.sort(reverse = True)
    minimum = 0
    for i in range(0, len(calorie)):
        minimum += (int(calorie[i]) * pow(2, i))
    return minimum

if __name__ == "__main__":
    n = int(input().strip())
    calorie = list(map(int, input().strip().split(' ')))
    result = marcsCakewalk(calorie)
    print(result)
```
