# Python Functionals

{% embed url="https://www.hackerrank.com/domains/python?badge_type=python&filters%5Bsubdomains%5D%5B%5D=py-functionals" %}

## Map and Lambda Function

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

```python
cube = lambda x: pow(x, 3)

def fibonacci(n):
    numbers = []
    
    for i in range(n):
        if i <= 1:
            numbers.append(i)
        else:
            numbers.append(numbers[len(numbers)-1] + numbers[len(numbers)-2])

    return numbers

if __name__ == '__main__':
    n = int(input())
    print(list(map(cube, fibonacci(n))))
```

***

## Validating Email Address with a Filter

<div>

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../.gitbook/assets/image (2) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

</div>

```python
import re

def fun(s):
    # return True if s is a valid email, else return False
    if re.match(r'^[a-zA-Z0-9_-]+@[a-zA-Z0-9]+\.[a-zA-Z]{1,3}$', s):
        return True
    else:
        return False
    

def filter_mail(emails):
    return list(filter(fun, emails))

if __name__ == '__main__':
    n = int(input())
    emails = []
    for _ in range(n):
        emails.append(input())

filtered_emails = filter_mail(emails)
filtered_emails.sort()
print(filtered_emails)
```

***

## Reduce Function

<figure><img src="../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption></figcaption></figure>

```python
from fractions import Fraction
from functools import reduce

def product(fracs):
    t = reduce(lambda x, y: x * y, fracs)
    return t.numerator, t.denominator

if __name__ == '__main__':
    fracs = []
    for _ in range(int(input())):
        fracs.append(Fraction(*map(int, input().split())))
    result = product(fracs)
    print(*result)
```
