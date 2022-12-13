# 約数数え上げ
計算量 $O\sqrt{N}$
## 使い方
```Python
l = make_divisors(36)
#->[1, 2, 3, 4, 6, 9, 12, 18, 36]

l = make_divisors(1)
#->[1]
```

## コード
```Python
def make_divisors(n):
    lower_divisors , upper_divisors = [], []
    i = 1
    while i*i <= n:
        if n % i == 0:
            lower_divisors.append(i)
            if i != n // i:
                upper_divisors.append(n//i)
        i += 1
    return lower_divisors + upper_divisors[::-1]
```
