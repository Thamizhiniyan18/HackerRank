# Grep

{% embed url="https://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples/" %}

{% embed url="https://tldp.org/LDP/Bash-Beginners-Guide/html/sect_04_02.html" %}

## Regexp Cheatsheet

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption><p>Source: <a href="https://regexr.com/">https://regexr.com/</a></p></figcaption></figure>

## 'Grep' #1

You are given a text file that will be piped into your command through STDIN. Use _grep_ to display all the lines that contain the word **the** in them. The search should be sensitive to case. Display only those lines of the input file that contain the word '_the_'.

```shell
grep -w the
```

***

## 'Grep' #2

You are given a text file that will be piped into your command through STDIN. Use _grep_ to display all those lines that contain the word **the** in them.\
_The search should NOT be sensitive to case._\
Display only those lines of the input file that contain the word '_the_'.

```shell
grep -i -w the
```

***

## 'Grep' #3

You are given a text file that will be piped into your command through STDIN. Use _grep_ to **remove** all those lines that contain the word '_that_'. The search should NOT be sensitive to case.

```shell
grep -i -w -v that
```

***

## 'Grep' - A

Given a text file, which will be piped to your command through STDIN, use grep to display all those lines which contain any of the following words in them: the that then those The search should not be sensitive to case. Display only those lines of an input file, which contain the required words.

```shell
grep -E -i -w "the|then|that|those"
```

***

## 'Grep' - B

Given an input file, with **N** credit card numbers, each in a new line, your task is to grep out and output only those credit card numbers which have two or more consecutive occurrences of the same digit (which may be separated by a space, if they are in different segments). Assume that the credit card numbers will have 4 space separated segments with 4 digits each.

If the credit card number is 1434 5678 9101 1234, there are two consecutive instances of 1 (though) as highlighted in box brackets: 1434 5678 910\[1] \[1]234

Here are some credit card numbers where consecutively repeated digits have been highlighted in box brackets. The last case does not have any repeated digits: 1234 5678 910\[1] \[1]234\
2\[9]\[9]\[9] 5178 9101 \[2]\[2]34\
\[9]\[9]\[9]\[9] 5628 920\[1] \[1]232\
8482 3678 9102 1232

```shell
grep "\(\d\)\s*\1"
```

##
