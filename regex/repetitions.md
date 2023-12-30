# Repetitions

{% embed url="https://www.hackerrank.com/domains/regex?filters%5Bsubdomains%5D%5B%5D=re-repetitions" %}

## Matching {x} Repititions

You have a test string _**S**_.\
Your task is to write a regex that will match _**S**_ using the following conditions:

* _**S**_ must be of length equal to **`45`**.
* The first **40** characters should consist of **`letters`**(both lowercase and uppercase), or of **`even digits`**.
* The last **5** characters should consist of **`odd digits`** or **`whitespace characters`**.

```regex
^[a-zA-z02468]{40}[13579\s]{5}$
```

***

## Matching {x, y} Repititions

You have a test string _**S**_.\
Your task is to write a regex that will match _**S**_ using the following conditions:

* _**S**_ should begin with **1** or **2** **`digits`**.
* After that, _**S**_ should have **3** or more **`letters`** (both lowercase and uppercase).
* Then _**S**_ should end with up to **3`.`** symbol(s). You can end with **0** to **3**`.` symbol(s), inclusively.

```regex
^\d{1,2}[a-zA-Z]{3,}\.{,3}$
```

***

## Matching Zero Or More Repititions

You have a test string _**S**_.\
Your task is to write a regex that will match _**S**_ using the following conditions:

* _**S**_ should begin with **2** or more **`digits`**.
* After that, _**S**_ should have **0** or more **`lowercase letters`**.
* _**S**_ should end with **0** or more **`uppercase letters`**

```regex
^\d{2,}[a-z][A-Z]$
```

***

## Matching One Or More Repititions

You have a test string _**S**_.\
Your task is to write a regex that will match _**S**_ using the following conditions:

* _**S**_ should begin with **1** or more **`digits`**.
* After that, _**S**_ should have **1** or more **`uppercase letters`**.
* _**S**_ should end with **1** or more **`lowercase letters`**.

```regex
^\d+[A-Z]+[a-z]+$
```

***

## Matching Ending Items

Write a RegEx to match a test string, _**S**_, under the following conditions:

* _**S**_ should consist of only lowercase and uppercase letters (no numbers or symbols).
* _**S**_ should end in `s`.

```regex
^[a-zA-Z]*s$
```
