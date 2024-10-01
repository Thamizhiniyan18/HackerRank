# Assertions

{% embed url="https://www.hackerrank.com/domains/regex?filters%5Bsubdomains%5D%5B%5D=assertions" %}

## Positive Lookahead

<figure><img src="../.gitbook/assets/image (95).png" alt=""><figcaption></figcaption></figure>

```regex
o(?=oo)
```

***

## Negative Lookahead

<figure><img src="../.gitbook/assets/image (94).png" alt=""><figcaption></figcaption></figure>

```regex
(.)(?!\1)+
```

***

## Positive Lookbehind

**`JavaScript do not support lookbehind.`**

<figure><img src="../.gitbook/assets/image (96).png" alt=""><figcaption></figcaption></figure>

```regex
(?<=[13579])\d
```

***

## Negative Lookbehind

**`JavaScript do not support lookbehind.`**

<figure><img src="../.gitbook/assets/image (97).png" alt=""><figcaption></figcaption></figure>

```regex
(?<![aeiouAEIOU]).
```

***
