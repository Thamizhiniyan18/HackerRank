# Sets

{% embed url="https://www.hackerrank.com/domains/python?badge_type=python&filters%5Bsubdomains%5D%5B%5D=py-sets" %}

## Introduction to Sets

<figure><img src="../.gitbook/assets/image (2) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
def average(array):
    distinct = set(array)
    return sum(distinct) / len(distinct)

if __name__ == '__main__':
    n = int(input())
    arr = list(map(int, input().split()))
    result = average(arr)
    print(result)
```
{% endcode %}

***

## Set .add()

<figure><img src="../.gitbook/assets/image (2) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
distinct = set()

for _ in range(int(input())):
    distinct.add(input())
    
print(len(distinct))
```
{% endcode %}

***

## Set .discard(), .remove(), .pop()

<figure><img src="../.gitbook/assets/image (3) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
n = int(input())
s = set(map(int, input().split()))

for _ in range(int(input())):
    command = input().split()
    
    if command[0] == "discard":
        s.discard(int(command[1]))
    elif command[0] == "remove":
        s.remove(int(command[1]))
    elif command[0] == "pop":
        s.pop()
        
print(sum(s))
```
{% endcode %}

***

## Set .union() Operation

<figure><img src="../.gitbook/assets/image (4) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
n = int(input())
english_newspaper = set(map(int, input().split()))
m = int(input())
french_newspaper = set(map(int, input().split()))

print(len(english_newspaper.union(french_newspaper)))
```
{% endcode %}

***

## Set .intersection() Operation

<figure><img src="../.gitbook/assets/image (5) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
n = int(input())
english_newspaper = set(map(int, input().split()))
m = int(input())
french_newspaper = set(map(int, input().split()))

print(len(english_newspaper.intersection(french_newspaper)))
```
{% endcode %}

***

## Set .difference() Operation

<figure><img src="../.gitbook/assets/image (6) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
n = int(input())
english_newspaper = set(map(int, input().split()))
m = int(input())
french_newspaper = set(map(int, input().split()))

print(len(english_newspaper.difference(french_newspaper)))
```
{% endcode %}

***

## Set .symmetric\_difference() Operation

<figure><img src="../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
n = int(input())
english_newspaper = set(map(int, input().split()))
m = int(input())
french_newspaper = set(map(int, input().split()))

print(len(english_newspaper.symmetric_difference(french_newspaper)))
```
{% endcode %}

***

## Symmetric Difference

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
m = int(input())
M = set(map(int, input().split()))
n = int(input())
N = set(map(int, input().split()))

for each in sorted(M.symmetric_difference(N)):
    print(each)
```
{% endcode %}

***

## Set Mutations

<figure><img src="../.gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
n = int(input())
set_a = set(map(int, input().strip().split()))

for _ in range(int(input())):
    command = input().strip().split()
    set_b = set(map(int, input().strip().split()))
    if command[0] == "intersection_update":
        set_a.intersection_update(set_b)
    if command[0] == "symmetric_difference_update":
        set_a.symmetric_difference_update(set_b)
    if command[0] == "difference_update":
        set_a.difference_update(set_b)
    if command[0] == "update":
        set_a.update(set_b)
        
print(sum(set_a))
```
{% endcode %}

***

## The Captain's Room

<figure><img src="../.gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
K = int(input())
room_numbers = list(map(int, input().split()))
distinct_room_numbers = set(room_numbers)

for each in distinct_room_numbers:
    room_numbers.remove(each)

print(distinct_room_numbers.difference(set(room_numbers)).pop())
```
{% endcode %}

***

## Check Subset

<figure><img src="../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
for _ in range(int(input())):
    a = int(input())
    A = set(map(int, input().split()))
    b = int(input())
    B = set(map(int, input().split()))
    
    if A.issubset(B):
        print(True)
    else:
        print(False)
```
{% endcode %}



***

## Check Strict Superset



<figure><img src="../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
A = set(map(int, input().split()))

for _ in range(int(input())):
    if A.issuperset(set(map(int, input().split()))):
        pass
    else:
        print(False)
        exit()
    
print(True)
```
{% endcode %}

***

## No Idea!

<figure><img src="../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
happiness = 0

n, m = map(int, input().split())
arr = list(map(int, input().split()))
A = set(map(int, input().split()))
B = set(map(int, input().split()))

for each in arr:
    if each in A:
        happiness += 1
    if each in B:
        happiness -= 1
        
print(happiness)
```
{% endcode %}
