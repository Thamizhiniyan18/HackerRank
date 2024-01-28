# Collections

{% embed url="https://www.hackerrank.com/domains/python?badge_type=python&filters%5Bsubdomains%5D%5B%5D=py-collections" %}

## Collections.Counter()

<figure><img src="../.gitbook/assets/image (73).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
from collections import Counter

x = int(input())
shoe_sizes = Counter(map(int, input().split()))
n = int(input())

earned = 0

for i in range(n):
    desired_size, price = map(int, input().split())
    
    if shoe_sizes[desired_size] > 0:
        earned += price
        shoe_sizes[desired_size] -= 1
    
print(earned)
```
{% endcode %}

***

## DefaultDict Tutorial

<figure><img src="../.gitbook/assets/image (74).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
from collections import defaultdict

n, m = map(int, input().split())

A = defaultdict(list)

for index in range(n):
    A[input()].append(str(index + 1))

B = [input() for _ in range(m)]

for each in B:
    print(" ".join(A[each])) if each in A.keys() else print("-1")
```
{% endcode %}

***

## Collections.namedtuple()

<figure><img src="../.gitbook/assets/image (75).png" alt=""><figcaption></figcaption></figure>

<pre class="language-python" data-line-numbers><code class="lang-python"><strong>from collections import namedtuple
</strong>
n = int(input())

columns = namedtuple('columns', input())

rows = [columns(*input().split()) for _ in range(n)]
    
print(sum([int(each.MARKS) for each in rows]) / n)
</code></pre>

***

## Collections.OrderedDict()

<figure><img src="../.gitbook/assets/image (76).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
from collections import OrderedDict

ordered_dict = OrderedDict()

for _ in range(int(input())):
    item, quantity = input().strip().rsplit(maxsplit=1)
    
    if item in ordered_dict:
        ordered_dict[item] += int(quantity)
    else:
        ordered_dict[item] = int(quantity)

for each in ordered_dict.items():
    print(*each)
```
{% endcode %}

***

## Collections.deque()

<figure><img src="../.gitbook/assets/image (77).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
from collections import deque

d = deque()

for _ in range(int(input())):
    operation = input().split()
    
    if operation[0] == "append":
        d.append(int(operation[1]))
    if operation[0] == "appendleft":
        d.appendleft(int(operation[1]))
    if operation[0] == "pop":
        d.pop()
    if operation[0] == "popleft":
        d.popleft()
        
print(" ".join(map(str, d)))
```
{% endcode %}

***

## Word Order

<figure><img src="../.gitbook/assets/image (78).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
from collections import OrderedDict

d = OrderedDict()

for _ in range(int(input())):
    i = input()
    
    if i not in d:
        d[i] = 0
    
    d[i] += 1
    
print(len(d))

print(" ".join(map(str, d.values())))
```
{% endcode %}

***

## Company Logo

<figure><img src="../.gitbook/assets/image (71).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
from collections import Counter
from itertools import chain

s = input()

d = Counter(s)

top_3 = [sorted([i for i in d.items() if i[1] == each]) for each in sorted(set(d.values()), reverse=True)[:3]]

for each in list(chain(*top_3))[:3]:
    print(" ".join(map(str, each)))
```
{% endcode %}

***

## Piling Up!

<figure><img src="../.gitbook/assets/image (72).png" alt=""><figcaption></figcaption></figure>

### Using Iteration - Efficient

{% code lineNumbers="true" %}
```python
from collections import deque


def piling(blocks, direction):
    stack = [blocks.popleft() if direction == "left" else blocks.pop()]
    possible = True

    while possible and len(blocks) > 0:
        if stack[-1] >= blocks[0] and stack[-1] >= blocks[-1]:
            if blocks[0] > blocks[-1]:
                stack.append(blocks.popleft())
                continue
            if blocks[-1] > blocks[0]:
                stack.append(blocks.pop())
                continue

        if stack[-1] >= blocks[0]:
            stack.append(blocks.popleft())
            continue

        if stack[-1] >= blocks[-1]:
            stack.append(blocks.pop())
            continue

        possible = False

    if not possible:
        return False

    if len(blocks) == 0:
        return True


for _ in range(int(input())):
    n = int(input())
    blocks_input = deque(map(int, input().split()))

    if piling(blocks_input.copy(), "left") or piling(blocks_input.copy(), "right"):
        print("Yes")
    else:
        print("No")
```
{% endcode %}

### Using Recursion - Not Efficient

{% code lineNumbers="true" %}
```python
from collections import deque
from sys import setrecursionlimit

setrecursionlimit(1000000)


def piling(blocks, stack, direction=None):
    if len(blocks) == 0:
        return True

    if direction == "left":
        if len(stack) == 0:
            stack.append(blocks.popleft())
            return piling(blocks, stack)

    if direction == "right":
        if len(stack) == 0:
            stack.append(blocks.pop())
            return piling(blocks, stack)

    if not direction:
        if stack[-1] >= blocks[0] and stack[-1] >= blocks[-1]:
            if blocks[-1] > blocks[0]:
                stack.append(blocks.pop())
                return piling(blocks, stack)

            if blocks[0] > blocks[-1]:
                stack.append(blocks.popleft())
                return piling(blocks, stack)

        if stack[-1] >= blocks[0]:
            stack.append(blocks.popleft())
            return piling(blocks, stack)

        if stack[-1] >= blocks[-1]:
            stack.append(blocks.pop())
            return piling(blocks, stack)

    return False


for _ in range(int(input())):
    n = int(input())
    blocks_input = deque(map(int, input().split()))

    if piling(blocks_input.copy(), [], "left") or piling(blocks_input.copy(), [], "right"):
        print("Yes")
    else:
        print("No")
```
{% endcode %}
