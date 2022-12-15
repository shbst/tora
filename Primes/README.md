# 素因数分解
計算量 $O(\sqrt{N})$
## 使い方

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

## コード
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
# エラトステネスの篩
計算量 $O(N \log \log N)$
## 使い方
```Python
n = 10
is_prime = sieve(n)
print(is_prime[5]) # True
print(is_prime[10]) # False
```

## コード
```Python
import math

# エラトステネスの篩
def sieve(n):
    is_prime = [True] * (n + 1)
    is_prime[0], is_prime[1] = False, False
    for i in range(2, int(math.sqrt(n)) + 1):
        if is_prime[i]:
            for j in range(2 * i, n + 1, i):
                is_prime[j] = False
    return is_prime
```
