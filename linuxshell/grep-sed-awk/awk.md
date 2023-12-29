# Awk

{% embed url="https://quickref.me/awk.html" %}

{% embed url="https://www.thegeekstuff.com/2010/01/awk-introduction-tutorial-7-awk-print-examples/" %}

{% embed url="https://www.thegeekstuff.com/2010/02/awk-conditional-statements/" %}

## 'Awk' - 1

You are given a file with four space separated columns containing the scores of students in three subjects. The first column contains a single character (A - Z), the student identifier. The next three columns have three numbers each. The numbers are between 0 and 100, both inclusive. These numbers denote the scores of the students in English, Mathematics, and Science, respectively.

Your task is to identify those lines that do not contain all three scores for students.

### Method 1

```shell
awk '!($2 && $3 && $4) {print "Not all scores are available for " $1}'
```

### Method 2

{% code lineNumbers="true" %}
```bash
awk '{
    if ( $2 == "" || $3 == "" || $4 == "" ) {
        print "Not all scores are available for", $1;
    }
}'
```
{% endcode %}

***

## 'Awk' - 2

You are given a file with four space separated columns containing the scores of students in three subjects. The first column contains a single character (A - Z), the student identifier. The next three columns have three numbers each. The numbers are between 0 and 100, both inclusive. These numbers denote the scores of the students in English, Mathematics, and Science, respectively.

Your task is to identify whether each of the students has passed or failed.\
A student is considered to have passed if (s)he has a score 50 or more in _each_ of the three subjects.

{% code lineNumbers="true" %}
```shell
awk '{
    grade="Pass"
    if ( $2<50 || $3<50 || $4<50) grade="Fail"
    print $1,":",grade
}'
```
{% endcode %}

***

## 'Awk' - 3

You are provided a file with four space-separated columns containing the scores of students in three subjects. The first column, contains a single character (A-Z) - the identifier of the student. The next three columns have three numbers (each between 0 and 100, both inclusive) which are the scores of the students in English, Mathematics and Science respectively.

Your task is to identify the performance grade for each student. If the average of the three scores is 80 or more, the grade is 'A'. If the average is 60 or above, but less than 80, the grade is 'B'. If the average is 50 or above, but less than 60, the grade is 'C'. Otherwise the grade is 'FAIL'.

{% code lineNumbers="true" %}
```shell
awk '{
    average = ( $2 + $3 + $4 ) / 3
    if ( average >= 80 ) print $0, ":", "A"
    else if ( average >= 60 ) print $0, ":", "B"
    else if ( average >= 50 ) print $0, ":", "C"
    else print $0, ":", "FAIL"
}'
```
{% endcode %}

***

## 'Awk' - 4

You are provided a file with four space-separated columns containing the scores of students in three subjects. The first column, contains a single character (A-Z) - the identifier of the student. The next three columns have three numbers (each between 0 and 100, both inclusive) which are the scores of the students in English, Mathematics and Science respectively.

{% code lineNumbers="true" %}
```shell
awk '{
    printf ($0)
    if ( NR % 2 == 0 ) printf "\n"
    else printf ";"
}'
```
{% endcode %}
