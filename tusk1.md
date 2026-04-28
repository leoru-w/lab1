# Задача 1
Проверка наличия элемента в массиве
---
```python
import random
import time

def same_or_not(numb, mass):
    for i in range(len(mass)):
        if mass[i] == numb:
            return True
    return False

def generate_array(n):
    arr = []
    for i in range(n):
        arr.append(random.randint(0, 10000))
    return arr

def measure_time(func, mass, numb):
    start = time.perf_counter()
    func(numb, mass)
    end = time.perf_counter()
    return end - start

sizes = [100, 1000, 5000, 10000]
for n in sizes:
    arr= generate_array(n)
    h=random.randint(0, 10000)
    t = measure_time(same_or_not, arr, h )
    print(n, f"{t:.6f}",same_or_not(h,arr))
```
| n | t,с |
|---|---|
| 100 | 0.000004 |
| 1000 | 0.000026 |
| 5000 | 0.000125 |
| 10000 | 0.000188 |
