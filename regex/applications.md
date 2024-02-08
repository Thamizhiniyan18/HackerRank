# Applications

{% embed url="https://www.hackerrank.com/domains/regex?filters%5Bsubdomains%5D%5B%5D=re-applications" %}

## Detect HTML Tags

<figure><img src="../.gitbook/assets/image (10) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re

regex_pattern = r'<[a-z\d]+\b'

tags = set()

for i in range(0, int(input())):
    line = input()
    result = re.findall(regex_pattern, line)
    for each in result:
        tags.add(each.replace("<", ""))
    
print(";".join(sorted(tags)))
```
{% endcode %}

***

## Find A Sub-Word

<figure><img src="../.gitbook/assets/image (12) (1).png" alt=""><figcaption></figcaption></figure>

### Method 1

{% code lineNumbers="true" %}
```python
import re

queries_dict = dict()

lines = [input() for _ in range(0, int(input()))]
queries = [input() for _ in range(0, int(input()))]

for line in lines:
    for query in queries:
        if query not in queries_dict:
            queries_dict[query] = 0
        result = re.findall(fr'\b\w+{query}\w+\b', line)
        queries_dict[query] += len(result)
      
for value in queries_dict.values():
    print(value)
```
{% endcode %}

### Method 2

{% code lineNumbers="true" %}
```python
import re

n = " ".join([(input()) for _ in range(int(input()))])

for _ in range(int(input())):
    print(len(re.findall(f"\\w{input()}\\w", n)))
```
{% endcode %}

***

## Alien Username

<figure><img src="../.gitbook/assets/image (14) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re

regex_pattern = r'^[_\.]\d+[a-zA-Z]*_?$'

for _ in range(0, int(input())):
    print("VALID") if re.findall(regex_pattern, input()) else print("INVALID")
```
{% endcode %}

***

## IP Address Validation

<figure><img src="../.gitbook/assets/image (15) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re

ipv4_regex_pattern = r'^(25[0-5]|2[0-4]\d|1\d{2}|\d\d?)\.(25[0-5]|2[0-4]\d|1\d{2}|\d\d?)\.(25[0-5]|2[0-4]\d|1\d{2}|\d\d?)\.(25[0-5]|2[0-4]\d|1\d{2}|\d\d?)$'
ipv6_regex_pattern = r'^[a-f\d]{0,4}:[a-f\d]{0,4}:?[a-f\d]{0,4}:?[a-f\d]{0,4}:?[a-f\d]{0,4}:?[a-f\d]{0,4}:?[a-f\d]{0,4}:[a-f\d]{0,4}$'

for i in range(0, int(input())):
    address = input()
    if re.findall(ipv4_regex_pattern, address):
        print("IPv4")
    elif re.findall(ipv6_regex_pattern, address):
        print("IPv6")
    else:
        print("Neither")
```
{% endcode %}

***

## Detecting Valid Latitude and Longitude Pairs

<figure><img src="../.gitbook/assets/image (19) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re

regex_pattern = r'\([\+-]?(90(\.0+)?|[0-8]\d(\.\d+)?|\d(\.\d+)?),\s[\+-]?(180(\.0+)?|1[0-7]\d(\.\d+)?|\d{1,2}(\.\d+)?)\)'

for _ in range(0, int(input())):
    print("Valid") if re.findall(regex_pattern, input()) else print("Invalid")
```
{% endcode %}

***

## HackerRank Tweets

<figure><img src="../.gitbook/assets/image (20) (1).png" alt=""><figcaption></figcaption></figure>

### Method 1

{% code lineNumbers="true" %}
```python
import re

regex_pattern = r'(?i)hackerrank' # Mode Modifiers

tweets = 0

for i in range(0, int(input())):
    if re.findall(regex_pattern, input()):
        tweets += 1
        
print(tweets)
```
{% endcode %}

### Method 2

{% code lineNumbers="true" %}
```python
import re

regex_pattern = r'[Hh][Aa][Cc][Kk][Ee][Rr]{2}[Aa][Nn][Kk]'

tweets = 0

for i in range(0, int(input())):
    if re.findall(regex_pattern, input()):
        tweets += 1
        
print(tweets)
```
{% endcode %}

***

## Build a Stack Exchange Scraper

<figure><img src="../.gitbook/assets/image (23) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re
import sys

identifier_regex = r'(?<=questions\/)\d+(?=\/)'
questions_regex = r'(?<=question-hyperlink">).+(?=<\/a>)'
time_regex = r'(?<=relativetime">).+(?=<\/span>)'

fragment = sys.stdin.read()

identifiers = re.findall(identifier_regex, fragment)
questions = re.findall(questions_regex, fragment)
time = re.findall(time_regex, fragment)

for each in zip(identifiers, questions, time):
    print(";".join(each))
```
{% endcode %}

***

## Utopian Identification Number

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re

regex_pattern = r'^[a-z]{0,3}\d{2,8}[A-Z]{3,}'

for i in range(0, int(input())):
    print("VALID") if re.findall(regex_pattern, input()) else print("INVALID")
```
{% endcode %}

***

## Valid Pan Format

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re

regex_pattern = r'^[A-Z]{5}\d{4}[A-Z]$'

for _ in range(int(input())):
    print("YES") if re.match(regex_pattern, input()) else print("NO")
```
{% endcode %}

***

## Find HackerRank

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re

starts_regex_pattern = r'^hackerrank\b'
ends_regex_pattern = r'\bhackerrank$'

for i in range(0, int(input())):
    conversation = input()
    isStartingWith = re.findall(starts_regex_pattern, conversation)
    isEndingWith = re.findall(ends_regex_pattern, conversation)
        
    if isStartingWith and isEndingWith:
        print("0")
    elif isStartingWith:
        print("1")
    elif isEndingWith:
        print("2")
    else:
        print("-1")
```
{% endcode %}

***

## Saying Hi

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re

regex_pattern = r'^[Hh][Ii]\s[^Dd]'

for _ in range(0, int(input())):
    sentence = input()
    
    if re.findall(regex_pattern, sentence):
        print(sentence)
```
{% endcode %}

***

## HackerRank Language

<figure><img src="../.gitbook/assets/image (9) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re

Regex_Pattern = r'^\d{5}\s(C|CPP|JAVA|PYTHON|PERL|PHP|RUBY|CSHARP|HASKELL|CLOJURE|BASH|SCALA|ERLANG|CLISP|LUA|BRAINFUCK|JAVASCRIPT|GO|D|OCAML|R|PASCAL|SBCL|DART|GROOVY|OBJECTIVEC)$'

for _ in range(0, int(input())):
    print("VALID") if re.findall(Regex_Pattern, input()) else print("INVALID")
```
{% endcode %}

***

## Split the Phone Numbers

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re

regex_pattern = r'^(?P<countryCode>\d{1,3})(-|\s)(?P<areaCode>\d{1,3})(-|\s)(?P<number>\d{4,10})$'

for _ in range(0, int(input())):
    matches = re.search(regex_pattern, input())
    print(f"CountryCode={matches.group('countryCode')},LocalAreaCode={matches.group('areaCode')},Number={matches.group('number')}")
```
{% endcode %}

***

## Detect HTML Attributes

<figure><img src="../.gitbook/assets/image (16) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re

tagsDict = dict()

for _ in range(0, int(input())):
    fragment = input()
    
    tags = re.findall(r'<[a-z\d]+\s?[\w\s="-:;?\[\]/]*/?>', fragment)
    for each in tags:
        tag = re.findall(r'<([a-z\d]+)', each)
        if tag[0] not in tagsDict.keys():
            tagsDict[tag[0]] = set()
        for attribute in re.findall(r'\s([a-z]+)(?==)', each):
            tagsDict[tag[0]].add(attribute)

for each in sorted(tagsDict.keys()):
    print(each + ":" + ",".join(sorted(tagsDict[each])))
```
{% endcode %}

***

## The British and American Style of Spelling

<figure><img src="../.gitbook/assets/image (17) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re

paragraph = ""

for _ in range(0, int(input())):
    paragraph += " " + input()
    
for _ in range(0, int(input())):
    print(len(re.findall(fr'{input()[:-2]}[zs]e', paragraph)))
```
{% endcode %}

***

## UK and US: Part 2

<figure><img src="../.gitbook/assets/image (18) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re

paragraph = ""

for _ in range(0, int(input())):
    paragraph += " " + input()

for _ in range(0, int(input())):
    ukWord = input()
    print(len(re.findall(fr'\b({ukWord}|{ukWord.replace("our", "or")})\b', paragraph)))
```
{% endcode %}

***

## Detect HTML Links

<figure><img src="../.gitbook/assets/image (3) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re

for _ in range(0, int(input())):
    fragment = input()
    
    aTags = re.findall(r'<a\shref=\"([\w$-_.+!*\'()/&?=:%\[\]]+)\"[^>]*(>.*?<)/a>', fragment)
    for each in aTags:
        link = each[0]
        text = re.findall(r'(?<=>)([\w\s.,/]+)(?=<)', each[1])
        print(link + "," + text[0].strip() if text else link + ",")
```
{% endcode %}

***

## Find a Word

<figure><img src="../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re

lines = ""

for _ in range(0, int(input())):
    lines += " " + input()
    
for _ in range(0, int(input())):
    word = input()
    
    print(len(re.findall(rf'\b{word}\b', lines)))
```
{% endcode %}

***

## Detect the Email Address

<figure><img src="../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re

emails = set()

for _ in range(0, int(input())):
    line = input()
    
    regex_emails = re.findall(r'\b[\w.]+@\w+[(\.\w+)]+\b', line)

    for each in regex_emails:
        emails.add(each)

print(";".join(sorted(emails)))
```
{% endcode %}

***

## Detect the Domain Name

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re

domains = set()

for _ in range(0, int(input())):
    line = input()
    
    regex_domains = re.findall(r'\bhttps?[(%3A)|:][(%2F)|/]{2}(?:[w\d]{3}.)?([\w\-]+\.(?:[\w\-]+\.)*[\w\-]+)\b', line)

    for each in regex_domains:
        domains.add(each)

print(";".join(sorted(domains)))
```
{% endcode %}

***

## Building a Smart IDE: Identifying comments

<figure><img src="../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import sys
import re

program = sys.stdin.read()

comments = re.findall(r'(//.*)|(/\*\*[\w^+.\s:\-,()]*\*\*/)|(/\*[\w^+.\s:\-,()]*\*/)', program)

for each in comments:
    for i in each:
        if i:
            for j in i.split("\n"):
                print(j.strip())
```
{% endcode %}

***

## Building a Smart IDE: Programming Language Detection

<figure><img src="../.gitbook/assets/image (6) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re
import sys

program = sys.stdin.read()

if re.search(r'#include<[a-z.]+>', program):
    print("C")
if re.search(r'import [a-zA-Z.\*]+;', program):
    print("Java")
if re.search(r'print (").*\1|class \w+:|def \w+\([\w,]*\):', program):
    print("Python")
```
{% endcode %}
