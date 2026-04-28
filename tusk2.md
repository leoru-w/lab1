# Задача 2
Поиск второго максимального элемента массива
---
```python
import random
import time


def V_max(arr):
    max1 = arr[0]
    max2 = arr[0]
    for i in range(len(arr)):
        if arr[i] > max1:
            max2 = max1
            max1 = arr[i]
        elif arr[i] > max2 and arr[i] != max1:
            max2 = arr[i]
    return max2


def generate_array(n):
    arr = []
    for i in range(n):
        arr.append(random.randint(0, 10000))
    return arr


def measure_time(func, data):
    start = time.perf_counter()
    result = func(data)
    end = time.perf_counter()
    return end - start, result


sizes = [100, 1000, 5000, 10000]
for n in sizes:
    arr = generate_array(n)
    dur, sec_max = measure_time(V_max, arr)
    print(n, f"{dur:.7f}", sec_max)
```
| n | t,с |
|---|---|
| 100 | 0.0000049 |
| 1000 | 0.0000317 |
| 5000 | 0.0001452 |
| 10000 | 0.0003211 |  
