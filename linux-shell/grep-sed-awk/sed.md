# Sed

{% embed url="https://www.grymoire.com/Unix/Sed.html#uh-10a" %}

{% embed url="https://tldp.org/LDP/abs/html/x23170.html" %}

{% embed url="https://www.folkstalk.com/2012/01/sed-command-in-unix-examples.html" %}

## 'Sed' Command #1

For each line in a given input file, transform the **first** occurrence of the word '_the_' with '_this_'. The search and transformation should be strictly case sensitive.

```shell
sed 's/\bthe\b/this/'
```

***

## 'Sed' Command #2

For each line in a given input file, transform all the occurrences of the word '_thy_' with '_your_'. The search should be **case insensitive**, i.e. '_thy_', '_Thy_', '_tHy_' etc. should be transformed to '_your_'.

```shell
sed 's/\bthy\b/your/Ig'
```

***

## 'Sed' Command #3

Given an input file, in each line, highlight all the occurrences of 'thy' by wrapping them up in brace brackets. The search should be case-insensitive.

```shell
sed 's/thy/{&}/Ig'
```

***

## 'Sed' Command #4

Given n lines of credit card numbers, mask the first 2 digits of each credit card number with an asterisk (i.e., `*`) and print the masked card number on a new line. Each credit card number consists of four space-separated groups of four digits. For example, the credit card number `1234 5678 9101 1234` would be masked and printed as `**** **** **** 1234`.

```shell
sed 's/\(\d\{4\}\s\)\{2\}\(\d\{4\}\)/**** **** ****/g'
```

***

## 'Sed' Command #5

Given an input file, with **N** credit card numbers, each in a new line, your task is to **reverse the ordering of segments** in each credit card number. Assume that the credit card numbers will have 4 space separated segments with 4 digits each.

If the original credit card number is 1434 5678 9101 1234, transform it to 1234 9101 5678 1434.

```shell
sed -E 's/([0-9]+) ([0-9]+) ([0-9]+) ([0-9]+)/\4 \3 \2 \1/' 
```
