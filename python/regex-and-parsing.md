# Regex and Parsing

{% embed url="https://www.hackerrank.com/domains/python?badge_type=python&filters%5Bsubdomains%5D%5B%5D=py-regex" %}

## Detect Floating Point Number

<figure><img src="../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

```python
import re

for _ in range(int(input())):
    if re.match(r'^[+-]?\d*\.\d+$', input()):
        print(True)
    else:
        print(False)
```

***

## Re.split()

<figure><img src="../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

```python
regex_pattern = r'[,.]'	# Do not delete 'r'.

import re
print("\n".join(re.split(regex_pattern, input())))
```

***

## Group(), Groups() & Groupdict()

<figure><img src="../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>

```python
import re

matches = re.match(r".*?([a-zA-Z\d])\1.*", input())

if matches:
    print(matches.group(1))
else:
    print(-1)

```

***

## Re.findall() & Re.finditer()

<figure><img src="../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

```python
import re

matches = re.findall(r"(?<=[^aeiouAEIOU])([aeiouAEIOU]{2,})(?=[^aeiouAEIOU])", input())

if matches:
    for each in matches:
        print(each)
else:
    print(-1)
```

***

## Re.start() & Re.end()

<figure><img src="../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

```python
import re

s = input()
k = input()
match = list(re.finditer(rf"(?=({k}))", s))

if match:
    for each in match:
        print((each.start(1), each.end(1) - 1))
else:
    print((-1, -1))
```

***

## Validating Roman Numerals

<figure><img src="../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

```python
regex_pattern = r"^M{0,3}(C[MD]|D?C{0,3})(X[CL]|L?X{0,3})(I[XV]|V?I{0,3})$"

import re
print(str(bool(re.match(regex_pattern, input()))))
```

***

## Validating Phone Numbers

<figure><img src="../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

```python
import re

for _ in range(int(input())):
    match = re.match(r"^[789]\d{9}$", input())
    
    if match:
        print("YES")
    else:
        print("NO")
```

***

## Validating and Parsing Email Addresses

<figure><img src="../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

```python
import re
import email.utils

for _ in range(int(input())):
    parsedAddr = email.utils.parseaddr(input())
    match = re.match(r"^[a-zA-Z][\w\-\.]*@[a-zA-Z]+\.[a-zA-Z]{1,3}$", parsedAddr[1])
    
    if match:
        print(email.utils.formataddr(parsedAddr))
```

***

## Hex Color Code

<figure><img src="../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

```python
import re
import sys

css = sys.stdin.read()

for each in re.findall(r"[ ,:](#[\dabcdefABCDEF]{6}|#[\dabcdefABCDEF]{3})", css):
    print(each)
```

***

## HTML Parser - Part 1

<figure><img src="../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

```python
from html.parser import HTMLParser
import sys

html = sys.stdin.read()


class MyHTMLParser(HTMLParser):
    def handle_starttag(self, tag, attrs):
        print("Start".ljust(5) + " :", tag)
        for attr in attrs:
            print(f'-> {attr[0]} > {attr[1]}')

    def handle_endtag(self, tag):
        print("End".ljust(5) + " :", tag)

    def handle_startendtag(self, tag, attrs):
        print("Empty".ljust(5) + " :", tag)
        for attr in attrs:
            print(f'-> {attr[0]} > {attr[1]}')


parser = MyHTMLParser()

parser.feed(html)
```

***

## HTML Parser - Part 2

<figure><img src="../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

```python
from html.parser import HTMLParser
import sys

n = int(input())
html = sys.stdin.read()


class MyHTMLParser(HTMLParser):
    def handle_comment(self, data):
        if len(data.split('\n')) > 1:
            print(">>> Multi-line Comment")
            print(data)
        else:
            print(">>> Single-line Comment")
            print(data)

    def handle_data(self, data):
        if data != "\n":
            print(">>> Data")
            print(data)


parser = MyHTMLParser()

parser.feed(html)
```

***

## Detect HTML Tags, Attributes and Attribute Values

<figure><img src="../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

```python
from html.parser import HTMLParser
import sys

html = sys.stdin.read()


class MyHTMLParser(HTMLParser):
    def handle_starttag(self, tag, attrs):
        print(tag)
        for attr in attrs:
            print(f'-> {attr[0]} > {attr[1]}')

    def handle_startendtag(self, tag, attrs):
        print(tag)
        for attr in attrs:
            print(f'-> {attr[0]} > {attr[1]}')


parser = MyHTMLParser()

parser.feed(html)
```

***

## Validating UID

<figure><img src="../.gitbook/assets/image (53).png" alt=""><figcaption></figcaption></figure>

```python
import re

for _ in range(int(input())):
    if re.match(r"^(?!.*(.).*\1)(?=.*[A-Z].*[A-Z])(?=.*\d.*\d.*\d)[A-Za-z0-9]{10}$", input()):
        print("Valid")
    else:
        print("Invalid")
```

***

## Regex Substitution

<figure><img src="../.gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

```python
import re
import sys

n = int(input())
html = sys.stdin.read()

print(re.sub(r'(?<= )\|\|(?= )', 'or', re.sub(r'(?<= )&&(?= )', 'and', html)))
```

***

## Validating Credit Card Numbers

<figure><img src="../.gitbook/assets/image (48).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (49).png" alt=""><figcaption></figcaption></figure>

```python
import re

for _ in range(int(input())):
    if re.match(r'^[456]\d(\d)(?!\1\-?\1{2})\d(-?)\d{2}(\d)(?!\3\-?\3{2})\d\2\d{2}(\d)(?!\4\-?\4{2})\d\2\d{2}(\d)(?!\5\-?\5{2})\d$', input()):
        print('Valid')
    else:
        print('Invalid')
```

***

## Validating Postal Code

<figure><img src="../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (51).png" alt=""><figcaption></figcaption></figure>

```python
# Use PyPy3
regex_integer_in_range = r'^[1-9]\d{5}$'	# Do not delete 'r'.
regex_alternating_repetitive_digit_pair = r'(\d)(?=\d\1)'	# Do not delete 'r'.


import re
P = input()

print (bool(re.match(regex_integer_in_range, P)) 
and len(re.findall(regex_alternating_repetitive_digit_pair, P)) < 2)
```

***

## Matrix Script

<figure><img src="../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

```python
import re

n, m = map(int, input().strip().split())

matrix = [list(input()) for _ in range(n)]

decodedScript = "".join(["".join(each) for each in list(zip(*matrix))])

print(re.sub(r'\b\W+\b', ' ', decodedScript))
```
