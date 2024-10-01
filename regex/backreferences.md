# Backreferences

{% embed url="https://www.hackerrank.com/domains/regex?filters%5Bsubdomains%5D%5B%5D=backreferences" %}

## Matching Same Text Again & Again

<figure><img src="../.gitbook/assets/image (89).png" alt=""><figcaption></figcaption></figure>

```regex
([a-z]\w\s\W\d\D[A-Z][a-zA-Z][aeiouAEIOU]\S)\1
```

***

## Backreferences to Failed Groups

You have a test string S.\
Your task is to write a regex which will match S, with following condition(s):

* S consists of 8 digits.
* S may have "-" separator such that string S gets divided in 4 parts, with each part having exactly two digits. (Eg. 12-34-56-78)

```regex
^\d{2}(-?)\d{2}\1\d{2}\1\d{2}$
```

***

## Branch Reset Groups

<figure><img src="../.gitbook/assets/image (90).png" alt=""><figcaption></figcaption></figure>

```regex
^\d{2}(-(?:--)?|\.|:)\d{2}\1\d{2}\1\d{2}$
```

***

## Forward References

<figure><img src="../.gitbook/assets/image (91).png" alt=""><figcaption></figcaption></figure>

```regex
^(\2tic|(tac))+$
```
