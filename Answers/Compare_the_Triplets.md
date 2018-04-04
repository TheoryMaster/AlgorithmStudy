Birthday Chocolate
===
[링크](https://www.hackerrank.com/challenges/compare-the-triplets/problem)  


문제요약
---
밥과 앨리스는 각각의 3가지 난이도의 문제를 풀어 점수를 갖는다.
밥과 앨리스의 점수를 각각 비교하여 두 사람의 포인트를 비교한다.

문제분석
---
함수의 매개변수로 6개의 점수가 들어오는데 이 점수를 각각 비교할 수 있도록 리스트에 저장,
앨리스와 밥의 포인트는 각각 0점으로 시작
반복문을 사용하여 두 사람의 점수를 비교하여 더 높은 점수의 사람에게 1 포인트
두 사람의 점수가 같을 경우에는 아무에게도 점수를 주지 않는다.
반복이 끝나면 점수를 반환하여 출력


소스코드
---
```python
#!/bin/python3

import os
import sys

#
# Complete the solve function below.
#
def solve(a0, a1, a2, b0, b1, b2):
    #
    score = [0, 0]
    a = [a0, a1, a2]
    b = [b0, b1, b2]
    for i in range(0,3):
        if(a[i] > b[i]):
            score[0] += 1
        elif(a[i] < b[i]):
            score[1] += 1

    return score
    #

if __name__ == '__main__':
    f = open(os.environ['OUTPUT_PATH'], 'w')

    a0A1A2 = input().split()

    a0 = int(a0A1A2[0])

    a1 = int(a0A1A2[1])

    a2 = int(a0A1A2[2])

    b0B1B2 = input().split()

    b0 = int(b0B1B2[0])

    b1 = int(b0B1B2[1])

    b2 = int(b0B1B2[2])

    result = solve(a0, a1, a2, b0, b1, b2)

    f.write(' '.join(map(str, result)))
    f.write('\n')

    f.close()
```
