#How to use

```
n = 5
uf = UnionFind(n)
uf.unite(1, 2)
uf.unite(4, 3)
uf.unite(4, 5)

uf.find(1) #->returns root
uf.find(4)

uf.same(1, 2) #->returns bool
uf.same(1, 3)
```
