# Strings

{% embed url="https://www.hackerrank.com/domains/python?badge_type=python&filters%5Bsubdomains%5D%5B%5D=py-strings" %}

## sWAP cASE

<figure><img src="../.gitbook/assets/image (133).png" alt=""><figcaption></figcaption></figure>

### Using swapcase()

```python
def swap_case(s):
    return s.swapcase()

if __name__ == '__main__':
    s = 'HackerRank.com presents "Pythonist 2".'
    print(swap_case(s))
```

### Using List Comprehension

```python
def swap_case(s):
    return ''.join(each.upper() if each.islower() else each.lower() for each in s)

if __name__ == '__main__':
    s = 'HackerRank.com presents "Pythonist 2".'
    print(swap_case(s))
```

***

## String Split and Join

<figure><img src="../.gitbook/assets/image (134).png" alt=""><figcaption></figcaption></figure>

```python
def split_and_join(line):
    return "-".join(line.split())

if __name__ == '__main__':
    line = input()
    result = split_and_join(line)
    print(result)
```

***

## What is Your Name?

<figure><img src="../.gitbook/assets/image (135).png" alt=""><figcaption></figcaption></figure>

```python
def print_full_name(first, last):
    print(f'Hello {first} {last}! You just delved into python.')

if __name__ == '__main__':
    first_name = input()
    last_name = input()
    print_full_name(first_name, last_name)
```

***

## Mutations

<figure><img src="../.gitbook/assets/image (136).png" alt=""><figcaption></figcaption></figure>

### Using List

```python
def mutate_string(string, position, character):
    ls = list(string)
    ls[position] = character
    return ''.join(ls)

if __name__ == '__main__':
    s = input()
    i, c = input().split()
    s_new = mutate_string(s, int(i), c)
    print(s_new)
```

### Using Slice

```python
def mutate_string(string, position, character):
    return s[:position] + character + s[position + 1:]

if __name__ == '__main__':
    s = input()
    i, c = input().split()
    s_new = mutate_string(s, int(i), c)
    print(s_new)
```

***

## Find a String

<figure><img src="../.gitbook/assets/image (137).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
def count_substring(string, sub_string):
    count = 0
    
    for i in range(len(string)):
        if string[i:i + len(sub_string)] == sub_string:
            count += 1
    
    return count

if __name__ == '__main__':
    string = input().strip()
    sub_string = input().strip()
    
    count = count_substring(string, sub_string)
    print(count)
```
{% endcode %}

***

## String Validators

<figure><img src="../.gitbook/assets/image (138).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
def isAlphaNumeric(s):
    for i in s:
        if i.isalnum():
            return True
    return False

def isAlphabetic(s):
    for i in s:
        if i.isalpha():
            return True
    return False

def isDigit(s):
    for i in s:
        if i.isdigit():
            return True
    return False

def isLower(s):
    for i in s:
        if i.islower():
            return True
    return False

def isUpper(s):
    for i in s:
        if i.isupper():
            return True
    return False


if __name__ == '__main__':
    s = input()

    print(isAlphaNumeric(s))
    print(isAlphabetic(s))
    print(isDigit(s))
    print(isLower(s))
    print(isUpper(s))
```
{% endcode %}

***

## Text Alignment

<figure><img src="../.gitbook/assets/image (139).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
def main():
    thickness = int(input())
    c = 'H'

    # Top Cone
    for i in range(thickness):
        print((c * i).rjust(thickness - 1) + c + (c * i).ljust(thickness - 1))

    # Top Pillars
    for i in range(thickness + 1):
        print((c * thickness).center(thickness * 2) + (c * thickness).center(thickness * 6))

    # Middle Belt
    for i in range((thickness + 1) // 2):
        print((c * thickness * 5).center(thickness * 6))

    # Bottom Pillars
    for i in range(thickness + 1):
        print((c * thickness).center(thickness * 2) + (c * thickness).center(thickness * 6))
        
    # Bottom Cone
    for i in range(thickness):
        print(((c * (thickness - i - 1)).rjust(thickness) + c + (c * (thickness - i - 1)).ljust(thickness)).rjust(
            thickness * 6))


if __name__ == "__main__":
    main()
```
{% endcode %}

***

## Text Wrap

<figure><img src="../.gitbook/assets/image (140).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import textwrap

def wrap(string, max_width):
    return '\n'.join(textwrap.wrap(string, max_width))

if __name__ == '__main__':
    string, max_width = input(), int(input())
    result = wrap(string, max_width)
    print(result)
```
{% endcode %}

***

## Designer Door Mat

<figure><img src="../.gitbook/assets/image (128).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
def main():
    n, m = map(int, input().split(' '))
    pattern = '.|.'
    middle_point = ((n - 1) / 2) + 1

    for i in range(n):
        if i + 1 < middle_point:
            print(f'{f"{pattern * i}" + pattern + f"{pattern * i}"}'.center(m, '-'))
        elif i + 1 == middle_point:
            print('WELCOME'.center(m, '-'))
        else:
            print(f'{f"{pattern * (n - (i + 1))}" + pattern + f"{pattern * (n - (i + 1))}"}'.center(m, '-'))

if __name__ == "__main__":
    main()
```
{% endcode %}

***

## String Formatting

<figure><img src="../.gitbook/assets/image (129).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
def print_formatted(number):
    l = len(bin(number)[2:])
    for i in range(1, number + 1):
        print(f"{f'{i}'.rjust(l)} {f'{oct(i)}'[2:].rjust(l)} {f'{hex(i)}'[2:].upper().rjust(l)} {f'{bin(i)}'[2:].rjust(l)}" )

if __name__ == '__main__':
    n = int(input())
    print_formatted(n)
```
{% endcode %}

***

## Alphabet Rangoli

<figure><img src="../.gitbook/assets/image (130).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import string

def print_rangoli(n):
    alphabets = string.ascii_lowercase

    for i in range(n-1):
        print("-".join(list(alphabets[n - i:n][::-1] + alphabets[n - (i + 1):n])).center(((n - 1) * 4) + 1, "-"))

    for i in range(n):
        print("-".join(list(alphabets[i:n][::-1] + alphabets[i + 1:n])).center(((n - 1) * 4) + 1, "-"))

if __name__ == '__main__':
    n = int(input())
    print_rangoli(n)
```
{% endcode %}

***

## Capitalize!

```python
def solve(s):
    return ' '.join(each.capitalize() for each in s.strip().split(' ')) # Solution

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    s = input()

    result = solve(s)

    fptr.write(result + '\n')

    fptr.close()
```

***

## The Minion Game

<figure><img src="../.gitbook/assets/image (131).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
def minion_game(string):
    length_of_string = len(string)

    kev = sum(length_of_string - i for i in range(length_of_string) if string[i] in "AEIOU")
    stu = length_of_string * (length_of_string + 1) / 2 - kev

    if stu > kev:
        print(f"Stuart {int(stu)}")
    elif stu == kev:
        print("Draw")
    else:
        print(f"Kevin {int(kev)}")

if __name__ == '__main__':
    s = input()
    minion_game(s)
```
{% endcode %}

***

## Merge The Tools!

<figure><img src="../.gitbook/assets/image (132).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
from collections import OrderedDict

def merge_the_tools(string, k):
    for i in range(0, len(string.strip()), k):
        print(''.join(list(OrderedDict.fromkeys(string[i: i + k]).keys())))

if __name__ == '__main__':
    string, k = input(), int(input())
    merge_the_tools(string, k)
```
{% endcode %}
