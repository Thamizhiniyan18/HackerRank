# Introduction

{% embed url="https://www.hackerrank.com/domains/regex?filters%5Bsubdomains%5D%5B%5D=re-introduction" %}

## Matching Specific String

You have a test string S. Your task is to match the string `hackerrank`. This is case sensitive.

```regex
hackerrank
```

***

## Matching Anything But a Newline

You have a test string S. Your task is to write a regular expression that matches only and exactly strings of form: abc.def.ghi.jkx, where each variable a,b,c,d,e,f,g,h,i,j,k,x can be any single character except the newline.

```regex
^...\....\....\....$
```

***

## Matching Digits & Non-Digit Characters

You have a test string S. Your task is to match the pattern xxXxxXxxxx .Here x denotes a digit character, and X denotes a non-digit character.

```regex
\d{2}\D\d{2}\D\d{4}
```

***

## Matching Whitespace & Non-Whitespace Characters

You have a test string S. Your task is to match the pattern XXxXXxXX. Here, x denotes whitespace characters, and X denotes non-white space characters.

```regex
\S{2}\s\S{2}\s\S{2}
```

***

## Matching Word & Non-Word Character

You have a test string S. Your task is to match the pattern xxxXxxxxxxxxxxXxxx. Here x denotes any word character and  X denotes any non-word character.

```regex
\w{3}\W\w{10}\W\w{3}
```

***

## Matching Start & End

You have a test string S. Your task is to match the pattern Xxxxx.\
Here, x denotes a word character, and X denotes a digit.\
S must start with a digit X and end with `.` symbol.\
S should be 6 characters long only.

```regex
^\d\w{4}\.$
```
