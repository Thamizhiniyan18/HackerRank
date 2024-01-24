# Math

{% embed url="https://www.hackerrank.com/domains/python?badge_type=python&filters%5Bsubdomains%5D%5B%5D=sets&filters%5Bsubdomains%5D%5B%5D=py-math" %}

## Mod Divmod

### What's divmod

<figure><img src="../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

### Task

<figure><img src="../.gitbook/assets/image (56).png" alt=""><figcaption></figcaption></figure>

### Solution

{% code lineNumbers="true" %}
```python
a = int(input())
b = int(input())

print(a // b)
print(a % b)
print(divmod(a, b))
```
{% endcode %}

***

## Polar Coordinates

### What is Polar Coordinates

<figure><img src="../.gitbook/assets/image (54).png" alt=""><figcaption></figcaption></figure>

### Pythons mathematical functions for complex numbers

<figure><img src="../.gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>

### Task

<figure><img src="../.gitbook/assets/image (53).png" alt=""><figcaption></figcaption></figure>

### Solution

{% code lineNumbers="true" %}
```python
from cmath import phase

complex_number = complex(input())

print(abs(complex_number))
print(phase(complex_number))
```
{% endcode %}

***

## Power - Mod Power

### Introduction

<figure><img src="../.gitbook/assets/image (59).png" alt=""><figcaption></figcaption></figure>

### Task

<figure><img src="../.gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>

### Solution

{% code lineNumbers="true" %}
```python
a = int(input())
b = int(input())
m = int(input())

print(pow(a, b))
print(pow(a, b, m))
```
{% endcode %}

***

## Integer Come in All Sizes

<figure><img src="../.gitbook/assets/image (60).png" alt=""><figcaption></figcaption></figure>

<pre class="language-python"><code class="lang-python"><strong>a = int(input())
</strong>b = int(input())
c = int(input())
d = int(input())

print(pow(a, b) + pow(c, d))
</code></pre>

***

## Find Angle MBC

<figure><img src="../.gitbook/assets/image (61).png" alt=""><figcaption></figcaption></figure>

```python
from math import degrees, atan

AB = int(input())
BC = int(input())

print(str(round(degrees(atan(AB / BC)))) + chr(176))
```

***

## Triangle Quest

<figure><img src="../.gitbook/assets/image (62).png" alt=""><figcaption></figcaption></figure>

```python
for i in range(1,int(input())):
    print(((10**i-1)//9)*i)
```

***

## Triangle Quest 2

<figure><img src="../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>

```python
for i in range(1, int(input())+1):
    print(((10 ** i)//9) ** 2)
```
