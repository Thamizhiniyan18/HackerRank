# Itertools

{% embed url="https://www.hackerrank.com/domains/python?badge_type=python&filters%5Bsubdomains%5D%5B%5D=py-itertools" %}

## itertools.product()

<figure><img src="../.gitbook/assets/image (155).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
from itertools import product

A = map(int, input().split())
B = map(int, input().split())

print(" ".join(map(str, product(A, B))))
```
{% endcode %}

***

## itertools.permutations()

<figure><img src="../.gitbook/assets/image (156).png" alt=""><figcaption></figcaption></figure>

```python
from itertools import permutations

s, k = input().split()

print("\n".join(sorted(map("".join, permutations(s, int(k))))))
```

***

## itertools.combinations()

<figure><img src="../.gitbook/assets/image (157).png" alt=""><figcaption></figcaption></figure>

```python
from itertools import combinations

s, k = input().split()

for i in range(int(k)):
    print("\n".join(sorted("".join(sorted(each)) for each in combinations(s, i + 1))))
```

***

## itertools.combinations\_with\_replacement()

<figure><img src="../.gitbook/assets/image (158).png" alt=""><figcaption></figcaption></figure>

```python
from itertools import combinations_with_replacement

s, k = input().split()

print("\n".join(sorted("".join(sorted(each)) for each in combinations_with_replacement(s, int(k)))))
```

***

## Compress The String!

<figure><img src="../.gitbook/assets/image (159).png" alt=""><figcaption></figcaption></figure>

```python
from itertools import groupby

s = input()

print(" ".join(str((len(list(group)), int(value))) for value, group in groupby(s)))
```

***

## Iterables and Iterators

<figure><img src="../.gitbook/assets/image (160).png" alt=""><figcaption></figcaption></figure>

```python
from itertools import combinations

n = int(input())
letters = input().split()
k = int(input())

combos = list(combinations(letters, k))
print(len(list(each for each in combos if "a" in each)) / len(combos))
```

***

## Maximize It!

<figure><img src="../.gitbook/assets/image (161).png" alt=""><figcaption></figcaption></figure>

```python
from itertools import product

k, m = map(int, input().split())

arr = [list(map(lambda x: pow(int(x), 2), input().split()[1:])) for _ in range(k)]

print(max(map(lambda x: sum(x) % m, product(*arr))))
```
