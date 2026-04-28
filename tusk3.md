# Задача 3
Бинарный поиск

```python
import random
import time
def bin_search(arr,h):
    l=0
    r=len(arr)-1
    while l<=r:
        m=(l+r)//2
        if arr[m]==h:
            return True
        elif arr[m]>h:
            r=m-1
        else:
            l=m+1
    return False

def generate_array(n):
    arr = []
    for i in range(n):
        arr.append(random.randint(0, 10000))
    return sorted(arr)

def measure_time(func, arr, numb):
    start = time.perf_counter()
    func(arr, numb)
    end = time.perf_counter()
    return end - start

sizes = [100, 1000, 5000, 10000]
for n in sizes:
    arr = generate_array(n)
    h=random.randint(0,10000)
    t = measure_time(bin_search,arr, h)
    print(n, f"{t:.8f}", bin_search(arr,h))
```
| n | t,с |
|---|---|
| 100 | 0.00000290 |
| 1000 | 0.00000210 |
| 5000 | 0.00000250 |
| 10000 | 0.00000200 |

