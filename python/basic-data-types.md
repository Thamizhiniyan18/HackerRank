# Basic Data Types

{% embed url="https://www.hackerrank.com/domains/python?badge_type=python&filters%5Bsubdomains%5D%5B%5D=py-basic-data-types" %}

## Lists

<figure><img src="../.gitbook/assets/image (4) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
if __name__ == '__main__':
    N = int(input())

    LIST = list()

    for _ in range(N):
        instruction = input().strip().split(' ')

        if instruction[0] == "insert":
            LIST.insert(int(instruction[1]), int(instruction[2]))

        elif instruction[0] == "remove":
            LIST.remove(int(instruction[1]))

        elif instruction[0] == "append":
            LIST.append(int(instruction[1]))

        elif instruction[0] == "sort":
            LIST.sort()

        elif instruction[0] == "pop":
            LIST.pop()

        elif instruction[0] == "reverse":
            LIST.reverse()

        elif instruction[0] == "print":
            print(LIST)
```
{% endcode %}

***

## Find the Runner-Up Score!

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
if __name__ == '__main__':
    n = int(input())
    arr = map(int, input().split())

    print(sorted(set(list(arr)))[-2])
```
{% endcode %}

***

## Finding the Percentage

<figure><img src="../.gitbook/assets/image (3) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
if __name__ == '__main__':
    n = int(input())
    student_marks = {}
    for _ in range(n):
        name, *line = input().split()
        scores = list(map(float, line))
        student_marks[name] = scores
    query_name = input()
    
    print("%.2f" % (sum(student_marks[query_name]) / len(student_marks[query_name])))
```
{% endcode %}

***

## Nested Lists

<figure><img src="../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
if __name__ == '__main__':
    markSheet = []
    scores = []

    for i in range(0, int(input())):
        name = input()
        score = float(input())
        markSheet.append([name, score])
        scores.append(score)

    sec_low_grade = sorted(list(set(scores)))[1]

    for NAME, SCORE in sorted(markSheet):
        if SCORE == sec_low_grade:
            print(NAME)
```
{% endcode %}

***

## List Comprehensions

<figure><img src="../.gitbook/assets/image (10) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
if __name__ == '__main__':
    x = int(input())
    y = int(input())
    z = int(input())
    n = int(input())
    
    print(sorted([[i, j, k] for k in range(0, z + 1) for j in range(0, y + 1) for i in range(0, x + 1) if i + j + k != n]))
```
{% endcode %}

***

## Tuples

<figure><img src="../.gitbook/assets/image (5) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

```python
# Compile with Pypy3

if __name__ == '__main__':
    n = int(input())
    print(hash(tuple(map(int, input().split()))))
```
