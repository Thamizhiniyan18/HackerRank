# Errors and Exceptions

{% embed url="https://www.hackerrank.com/domains/python?filters%5Bsubdomains%5D%5B%5D=errors-exceptions" %}

## Exceptions

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
for i in range(int(input())):
    try:
        a, b = map(str, input().strip().split(' '))
        print(int(a) // int(b))
    except ValueError as e:
        print(f"Error Code: {e}")
    except ZeroDivisionError as e:
        print(f"Error Code: {e}")
```
{% endcode %}

***

## Incorrect Regex

<figure><img src="../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

```python
# Run with pypy3
import re

for _ in range(int(input())):
    regex = input()
    try:
        re.compile(regex)
        print(True)
    except re.error:
        print(False)
```
