# Applications

{% embed url="https://www.hackerrank.com/domains/regex?filters%5Bsubdomains%5D%5B%5D=re-applications" %}

## Detect HTML Tags

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

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

## HackerRank Language

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import re

Regex_Pattern = r'^\d{5}\s(C|CPP|JAVA|PYTHON|PERL|PHP|RUBY|CSHARP|HASKELL|CLOJURE|BASH|SCALA|ERLANG|CLISP|LUA|BRAINFUCK|JAVASCRIPT|GO|D|OCAML|R|PASCAL|SBCL|DART|GROOVY|OBJECTIVEC)$'

for _ in range(0, int(input())):
    print("VALID") if re.findall(Regex_Pattern, input()) else print("INVALID")
```
{% endcode %}
