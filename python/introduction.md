# Introduction

{% embed url="https://www.hackerrank.com/domains/python?badge_type=python&filters%5Bsubdomains%5D%5B%5D=py-introduction" %}

## Say "Hello, World!" With Python

```python
print("Hello, World!")
```

***

## Python If-Else

<figure><img src="../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

<pre class="language-python" data-line-numbers><code class="lang-python"><strong>if __name__ == "__main__":
</strong>    n = int(input().strip())
    if n % 2 != 0 or n % 2 == 0 and 6 &#x3C;= n &#x3C;= 20:
        print("Weird")
    elif n % 2 == 0 and 2 &#x3C;= n &#x3C;= 5 or n % 2 == 0 and n > 20:
        print("Not Weird")
</code></pre>

***

## Arithmetic Operators

<figure><img src="../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
if __name__ == '__main__':
    a = int(input())
    b = int(input())

    print(a + b)
    print(a - b)
    print(a * b)
```
{% endcode %}

***

## Python: Division

<figure><img src="../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
if __name__ == '__main__':
    a = int(input())
    b = int(input())

    print(a // b)
    print(a / b)
```
{% endcode %}

***

## Loops

<figure><img src="../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
if __name__ == '__main__':
    n = int(input())
    lst = list(range(0 , n))
    for each in lst:
        print(each * each)
```
{% endcode %}

***

## Write a Function

<figure><img src="../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
def is_leap(year):
    if year % 4 == 0 and year % 100 != 0 or year % 400 == 0:
        return True
    else:
        return False


if __name__ == "__main__":
    year = 1992
    print(is_leap(year))
```
{% endcode %}

***

## Print Function

<figure><img src="../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
if __name__ == '__main__':
    n = int(input())
    for i in range(1, n + 1):
        print(i, end="")
```
{% endcode %}
