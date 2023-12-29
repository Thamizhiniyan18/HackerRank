# Cut

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
