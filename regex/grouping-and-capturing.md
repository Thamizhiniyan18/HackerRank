# Grouping and Capturing

{% embed url="https://www.hackerrank.com/domains/regex?filters%5Bsubdomains%5D%5B%5D=grouping-and-capturing" %}

## Matching Word Boundaries

You have a test String S. Your task is to write a regex which will match word starting with vowel (a,e,i,o, u, A, E, I , O or U). The matched word can be of any length. The matched word should consist of letters (lowercase and uppercase both) only. The matched word must start and end with a word boundary.

```regex
\b[aeiouAEIOU][a-zA-Z]*\b
```

***

## Capturing and Non-Capturing Groups

You have a test String S.\
Your task is to write a regex which will match S with the following condition:

* S should have 3 or more consecutive repetitions of **`ok`**.

```regex
(ok){3,}
```

***

## Alternative Matching

Given a test string, s, write a RegEx that matches s under the following conditions:

* &#x20;must start with `Mr.`, `Mrs.`, `Ms.`, `Dr.` or `Er.`.
* The rest of the string must contain only _one or more_ English alphabetic letters (upper and lowercase).

```regex
^(Mr\.|Mrs\.|Ms\.|Dr\.|Er\.)[a-zA-Z]+$
```
