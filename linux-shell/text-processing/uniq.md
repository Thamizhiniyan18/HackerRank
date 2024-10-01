# Uniq

## 'Uniq' Command #1

In this challenge, we practice using the _uniq_ command to eliminate consecutive repetitions of a line when a text file is piped through it.

Given a text file, remove the consecutive repetitions of any line.

```shell
uniq
```

***

## 'Uniq' Command #2

In this challenge, we practice using the _uniq_ command to eliminate consecutive repetitions of a line when a text file is piped through it.

Given a text file, count the number of times each line repeats itself. Only consider consecutive repetitions. Display the space separated count and line, respectively. There shouldn't be any leading or trailing spaces. Please note that the _uniq -c_ command by itself will generate the output in a different format than the one expected here.

```shell
uniq -c | cut -c 7-
# ---------or---------- 
uniq -c | tr -s ' ' | cut -c 2
```

***

## 'Uniq' Command #3

Given a text file, count the number of times each line repeats itself (only consider consecutive repetions). Display the count and the line, separated by a space. There shouldn't be leading or trailing spaces. Please note that the _uniq -c_ command by itself will generate the output in a different format.

This time, compare consecutive lines in a **case insensitive** manner. So, if a line X is followed by case variants, the output should count all of them as the same (but display only the form **X** in the second column).

So, as you might observe in the case below: aa, AA and Aa are all counted as instances of 'aa'.

```shell
uniq -c -i | cut -c 7-
```

***

## 'Uniq' Command #4

Given a text file, display only those lines which are **not** followed or preceded by identical replications.

```shell
uniq -u
```
