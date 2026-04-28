# Задание 4
Построение таблицы умножения

```python
import random
import time


def table(n):
    arr=[]
    for i in range(1,n+1):
        row=[]
        for j in range(1,n+1):
            row.append(i*j)
        arr.append(row)
    return arr

def measure_time(func, n):
    start = time.perf_counter()
    func(n)
    end = time.perf_counter()
    return end - start

sizes = [100, 1000, 5000, 10000]

for n in sizes:
    t=measure_time(table, n)
    print(n,f"{t:.7f}")
```
| n | t,с |
|---|---|
| 100 | 0.0003936 |
| 1000 | 0.0461796 |
| 5000 | 1.2297493 |
| 10000 | 6.9282800 |
