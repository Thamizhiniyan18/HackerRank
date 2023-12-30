# Character Class

{% embed url="https://www.hackerrank.com/domains/regex?filters%5Bsubdomains%5D%5B%5D=re-character-class" %}

## Matching Specific Characters

You have a test string S.\
Your task is to write a regex that will match S with following conditions:

* S must be of length: **`6`**
* First character: **`1`**, **`2`** or **`3`**
* Second character: **`1`**, **`2`** or **`0`**
* Third character: **`x`**, **`s`** or **`0`**
* Fourth character: **`3`**, **`0`** , **`A`** or **`a`**
* Fifth character: **`x`**, **`s`** or **`u`**
* Sixth character: **`.`** or **`,`**

```regex
^[1-3][120][xs0][30Aa][xsu][\.,]$
```

***

## Excluding Specific Characters

You have a test string _**S**_.\
Your task is to write a regex that will match _**S**_ with the following conditions:

* _**S**_ must be of length **`6`**.
* First character should _not_ be a **`digit`** (**1, 2, 3, 4, 5, 6, 7, 8, 9** or **0**).
* Second character should _not_ be a **`lowercase vowel`** (_**a**_, _**e**_, _**i**_, _**o**_ or _**u**_).
* Third character should _not_ be **`b`**, **`c`**, **`D`** or **`F`**.
* Fourth character should _not_ be a **`whitespace character`** ( \r, \n, \t, \f or \<space> ).
* Fifth character should _not_ be a **`uppercase vowel`** (_**A**_, _**E**_, _**I**_, _**O**_ or _**U**_).
* Sixth character should _not_ be a **`.`** or **`,`** symbol.

```regex
^[^\d][^aeiou][^bcDF][^\s][^AEIOU][^\.,]$
```

***

## Matching Character Ranges

Write a RegEx that will match a string satisfying the following conditions:

* The string’s length is **>= 5**.
* The first character must be a lowercase English alphabetic character.
* The second character must be a _positive_ digit. Note that we consider zero to be neither positive nor negative.
* The third character must _not_ be a lowercase English alphabetic character.
* The fourth character must _not_ be an uppercase English alphabetic character.
* The fifth character must be an uppercase English alphabetic character.

```regex
^[a-z][1-9][^a-z][^A-Z][A-Z]
```
