# Built-Ins

{% embed url="https://www.hackerrank.com/domains/python?badge_type=python&filters%5Bsubdomains%5D%5B%5D=py-built-ins" %}

## Zipped!

<figure><img src="../.gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>

```python
n, x = map(int, input().split())

marks = [list(map(float, input().split())) for _ in range(x)]

for each in zip(*marks):
    print(sum(each) / x)
```

***

## Input()

<figure><img src="../.gitbook/assets/image (59).png" alt=""><figcaption></figcaption></figure>

```python
x, k = map(int, input().split())
    
print(True) if eval(input()) == k else print(False)
```

***

## Python Evaluation

<figure><img src="../.gitbook/assets/image (60).png" alt=""><figcaption></figcaption></figure>

```python
eval(input())
```

***

## Any or All

<figure><img src="../.gitbook/assets/image (61).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
n, integers = int(input()), list(map(int, input().split()))
print(all([each > 0 for each in integers]) and any([str(each) == str(each)[::-1] for each in integers]))
```
{% endcode %}

***

## Athlete Sort

<figure><img src="../.gitbook/assets/image (62).png" alt=""><figcaption></figcaption></figure>

```python
n, m = map(int, input().split())
details = [list(map(int, input().split())) for _ in range(n)]
k = int(input())

for each in sorted(details, key=lambda x: x[k]):
    print(*each)
```

***

## ginortS

<figure><img src="../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>

```python
import string

s = input()

order = string.ascii_letters + str([each for each in string.digits if int(each) % 2 != 0]) + str([each for each in string.digits if int(each) % 2 == 0])

print("".join(sorted(s, key=lambda x: order.index(x))))
```
