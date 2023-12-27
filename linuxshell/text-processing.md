# Text Processing

{% embed url="https://www.hackerrank.com/domains/shell?filters%5Bsubdomains%5D%5B%5D=textpro" %}

## Cut #1

Given N lines of input, print the 3rd character from each line as a new line of output. It is guaranteed that each of the lines of input will have a 3rd character.

```bash
cut -c 3
```

***

## Cut #2

Display the 2nd and 7th character from each line of text.

```bash
cut -c 2,7
```

***

## Cut #3

Display a range of characters starting at the 2nd position of a string and ending at the 7th position (both positions included).

```bash
cut -c 2-7
```

***

## Cut #4

Display the first four characters from each line of text.

```bash
cut -c -4
```

***

## Cut #5

Given a tab delimited file with several columns (tsv format) print the first three fields.

```bash
cut -f -3
```

***

## Cut #6

Print the characters from thirteenth position to the end.

```bash
cut -c 13-
```

***

## Cut #7

Given a sentence, identify and display its fourth word. Assume that the space (' ') is the only delimiter between words.

```bash
cut -d ' ' -f 4
```

***

## Cut #8

Given a sentence, identify and display its first three words. Assume that the space (' ') is the only delimiter between words.

```bash
cut -d ' ' -f -3
```

***

## Cut #9

Given a tab delimited file with several columns (tsv format) print the fields from second fields to last field.

```bash
cut -f 2-
```

***

## Head of a Text File #1

In this challenge, we practice using the _head_ command to display the first  lines of a text file.

Display the first  20 lines of an input file.

```
head -n 20
```

***

## Head of a Text File #2

In this challenge, we practice using the _head_ command to display the first n  characters of a text file.

Display the first 20 characters of an input file.

```bash
head -c 20
```

***

## Middle of a Text File

Display the lines (from line number 12 to 22, both inclusive) of a given text file.

```bash
head -n 22 | tail -n 11
```

***

## Tail of a Text File #1

In this challenge, we practice using the _tail_ command to display the last n lines of a text file.

Display the last 20 lines of an input file.

```bash
tail -n 20
```

***

## Tail of a Text File #2

In this challenge, we practice using the _tail_ command to display the last 20 characters of a text file.

Display the last 20 characters of an input file.

```bash
tail -c 20
```

***

## 'Tr' Command #1

In this challenge, we practice using the _tr_ command because it is a useful translation tool in Linux.

In a given fragment of text, replace all parentheses ( ) with box brackets \[ ].

```bash
tr '(' '[' | tr ')' ']'
# ---------or---------- 
tr '()' '[]'
```

***

## 'Tr' Command #2

In this challenge, we practice using the _tr_ command because it is a useful translation tool in Linux.

In a given fragment of text, delete all the lowercase characters a-z.

```shell
tr -d a-z
```

***

## 'Tr' Command #3

In a given fragment of text, replace all sequences of multiple spaces with just one space.

```shell
tr -s ' '
```

***

## Sort Command #1

In this challenge, we practice using the _sort_ command to sort input in text or TSV formats.

Given a text file, order the lines in lexicographical order.

```shell
sort -d
```

***

## Sort Command #2

In this challenge, we practice using the _sort_ command to sort input in text or TSV formats.

Given a text file, order the lines in reverse lexicographical order (i.e. _Z-A_ instead of _A-Z_).

```shell
sort -r
```

***

## Sort Command #3

In this challenge, we practice using the _sort_ command to sort input in text or TSV formats.

You are given a text file where each line contains a number. The numbers may be either an integer or have decimal places. There will be no extra characters other than the number or the newline at the end of each line. Sort the lines in ascending order - so that the first line holds the numerically smallest number, and the last line holds the numerically largest number.

```shell
sort -n
```

***

## Sort Command #4

You are given a file of text, where each line contains a number (which may be either an integer or have decimal places). There will be no extra characters other than the number or the newline at the end of each line. Sort the lines in **descending** order - - such that the first line holds the (numerically) largest number and the last line holds the (numerically) smallest number.

```shell
sort -n -r
```

***

## Sort Command #5

You are given a file of text,which contains temperature information about American cities, in TSV (tab-separated) format. The first column is the name of the city and the next four columns are the average temperature in the months of Jan, Feb, March and April (see the sample input). Rearrange the rows of the table in **descending order** of the values for the average temperature in January.

```shell
sort -t $'\t' -k 2 -n -r
```

***

## Sort Command #6

You are given a file of tab separated weather data (TSV). There is no header column in this data file.\
The first five columns of this data are: (a) the name of the city (b) the average monthly temperature in Jan (in Fahreneit). (c) the average monthly temperature in April (in Fahreneit). (d) the average monthly temperature in July (in Fahreneit). (e) the average monthly temperature in October (in Fahreneit).

You need to sort this file in ascending order of the second column (i.e. the average monthly temperature in January).

```shell
sort -t $'\t' -k 2 -n
```

***

## Sort Command #7

You are given a file of **pipe-delimited** weather data (TSV). There is no header column in this data file. The first five columns of this data are: (a) the name of the city (b) the average monthly temperature in Jan (in Fahreneit). (c) the average monthly temperature in April (in Fahreneit). (d) the average monthly temperature in July (in Fahreneit). (e) the average monthly temperature in October (in Fahreneit).

You need to sort this file in **descending order** of the second column (i.e. the average monthly temperature in January).

```shell
sort -t '|' -k 2 -n -r
```

***

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

***

## Paste - 1

In this challenge, we practice using the _paste_ command to merge lines of a given file.

You are given a CSV file where each row contains the name of a city and its state separated by a comma. Your task is to replace the newlines in the file with semicolons as demonstrated in the sample.

```shell
paste -s -d ';'
```

***

## Paste - 2

In this challenge, we practice using the paste command to merge lines of a given file.

You are given a CSV file where each row contains the name of a city and its state separated by a comma. Your task is to restructure the file so that three consecutive rows are folded into one line and are separated by semicolons.

```shell
paste -d ';' - - -
```

***

## Paste - 3

Given a CSV file where each row contains the name of a city and its state separated by a comma, your task is to replace the newlines in the file with tabs as demonstrated in the sample.

```shell
paste -s
```

***

## Paste - 4

Given a CSV file where each row contains the name of a city and its state separated by a comma, your task is to restructure the file in such a way, that three consecutive rows are folded into one, and separated by tab.

```shell
paste - - -
```
