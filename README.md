# Лабораторная работа 6

## Шаг 1. Реализация и оптимизация метода Ферма с помощью Cython

![image](https://github.com/user-attachments/assets/e022202f-bc15-48a4-ac86-3c49215fd89a)

## Шаг 2. Распараллеливание: потоки и процессы
```
import math

def fermat_factorization_cy(object N, object max_iter_val):
    if N % 2 == 0:
        return 2, N // 2

    x = math.isqrt(N) + 1
    count = 0
    while count < max_iter_val:
        y_squared = x * x - N
        if y_squared >= 0:
            y = math.isqrt(y_squared)
            if y * y == y_squared:
                return (x - y, x + y)
        x += 1
        count += 1
    return None
```
![image](https://github.com/user-attachments/assets/8230bf1b-9071-44e5-8d9c-52067a39042e)


## Шаг 3. Работа с GIL
![image](https://github.com/user-attachments/assets/d5c19319-5e48-4527-8453-5f37449a4278)
