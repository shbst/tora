# 使い方

1は空リストを返す。
```Python
print(prime_factorize(1))
# []

print(prime_factorize(36))
# [2, 2, 3, 3]

print(prime_factorize(840))
# [2, 2, 2, 3, 5, 7]
```

各要素が何回出現するかカウントする場合。
```Python
import collections
c = collections.Counter(prime_factorize(840))
print(c)
# Counter({2: 3, 3: 1, 5: 1, 7: 1})
```

# コード
```Python
def prime_factorize(n):
    a = []
    while n % 2 == 0:
        a.append(2)
        n //= 2
    f = 3
    while f * f <= n:
        if n % f == 0:
            a.append(f)
            n //= f
        else:
            f += 2
    if n != 1:
        a.append(n)
    return a
```
