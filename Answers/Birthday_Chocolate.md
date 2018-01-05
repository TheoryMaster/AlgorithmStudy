Birthday Chocolate
===
[링크](https://www.hackerrank.com/challenges/the-birthday-bar/problem)  


문제요약
---
릴리는 론의 생일생일을 맞아 초콜릿 조각을 주려한다.  
초콜릿은 n개의 조각으로 이루어져있고 각 조각 위에는 숫자가 적혀있다.  
릴리는 조각위의 합이 d인 m개의 초콜릿 조각을 론에게 주려한다.  
이 때 몇 개의 경우가 존재하는지 구하라.  

ex) 5개의 조각에는 [1, 2, 1, 3, 2]가 적혀있고, m = 2, d = 3이다.  
1. 첫 번째 조각에서 부터 두 조각의 숫자의 합은 3이다.  
2. 두 번째 조각에서 부터 두 조각의 숫자의 합은 3이다.  
따라서 2가지 경우가 존재한다.

문제분석
---
이 문제는 리스트에서 m개의 연속된 값의 합이 d와 같을 때 카운트를 1 증가시킨다.  
최소한의 반복으로 결과를 도출


소스코드
---
```python
#!/bin/python3

import sys

def solve(n, s, d, m):
    count = 0
    for i in range(0, n - m + 1):
        temp = 0
        for j in range(0, m):
            temp = temp + s[i+j]
        if(temp == d):
            count = count + 1
    return count

n = int(input().strip())
s = list(map(int, input().strip().split(' ')))
d, m = input().strip().split(' ')
d, m = [int(d), int(m)]
result = solve(n, s, d, m)
print(result)
```
