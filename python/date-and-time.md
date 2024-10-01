# Date and Time

{% embed url="https://www.hackerrank.com/domains/python?filters%5Bsubdomains%5D%5B%5D=py-date-time" %}

## Calender Module

<figure><img src="../.gitbook/assets/image (170).png" alt=""><figcaption></figcaption></figure>

```python
from calendar import weekday, day_name

month, date, year = map(int, input().split())

print(day_name[weekday(year, month, date)].upper())
```

***

## Time Delta

<figure><img src="../.gitbook/assets/image (171).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
from datetime import datetime


def time_delta(t1, t2):
    time_format = '%a %d %b %Y %H:%M:%S %z'
    time1 = datetime.strptime(t1, time_format)
    time2 = datetime.strptime(t2, time_format)
    print(int((abs(time1 - time2)).total_seconds()))


if __name__ == '__main__':
    for _ in range(int(input())):
        time_delta(input(), input())
```
{% endcode %}
