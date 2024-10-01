# Arrays In Bash

{% embed url="https://www.hackerrank.com/domains/shell?filters%5Bsubdomains%5D%5B%5D=arrays-in-bash" %}

{% embed url="https://www.thegeekstuff.com/2010/06/bash-array-tutorial/" %}

## Read in an Array

Given a list of countries, each on a new line, your task is to read them into an array and then display the entire array, with a _space_ between each of the countries' names.

### Method 1

```bash
countries=($(cat))
```

### Method 2

{% code lineNumbers="true" %}
```shell
#!/bin/bash

array=()

while read line; do
    array+=("$line")
done

echo "${array[@]}"
```
{% endcode %}

### Method 3

{% code lineNumbers="true" %}
```shell
while read country 
 do 
   countries=( ${countries[@]} $country )
done 

echo ${countries[@]}
```
{% endcode %}

### Method 4

{% code lineNumbers="true" %}
```shell
declare -a arr=(`cut -d $'\n' -f 1-`)
echo ${arr[@]}
```
{% endcode %}

### Method 5

{% code lineNumbers="true" %}
```shell
read -ra arr < <(paste -sd " ")
echo "${arr[@]}"
```
{% endcode %}

***

## Slice an Array

Given a list of countries, each on a new line, your task is to read them into an array. Then slice the array and display only the elements lying between positions 3 and 7, both inclusive. Indexing starts from 0.

```shell
declare -a arr=(`cut -d $"\n" -f 1`)
echo "${arr[@]:3:5}"
```

***

## Filter an Array with Patterns

We now transition to some basic examples of bash scripting for the purpose of text processing and data munging. In this challenge, we practice reading and filtering an array.

### Method 1

{% code lineNumbers="true" %}
```shell
countries=($(cat))
filtered=(${countries[@]/*[Aa]*/})
echo "${filtered[@]}"
```
{% endcode %}

### Method 2

{% code lineNumbers="true" %}
```bash
readarray -t countries
filtered_countries=()
for country in "${countries[@]}"; do
  if [[ ! "$country" =~ [aA] ]]; then
    filtered_countries+=("$country")
  fi
done
for filtered_country in "${filtered_countries[@]}"; do
  echo "$filtered_country"
done
```
{% endcode %}

***

## Concatenate an Array with itself

Given a list of countries, each on a new line, your task is to read them into an array. Then, concatenate the array with itself (_twice_) - so that you have a total of three repetitions of the original array - and then display the entire concatenated array, with a _space_ between each of the countries' names.

### Method 1

{% code lineNumbers="true" %}
```shell
countries=($(cat))
twice=("${countries[@]}" "${countries[@]}" "${countries[@]}")
echo "${twice[@]}" 
```
{% endcode %}

### Method 2

{% code lineNumbers="true" %}
```shell
countries=($(cat))
echo "${countries[@]} ${countries[@]} ${countries[@]}"
```
{% endcode %}

***

## Display an element of an Array

Given a list of countries, each on a new line, your task is to read them into an array and then display the element indexed at 3. Note that indexing starts from 0.

{% code lineNumbers="true" %}
```shell
countries=($(cat))
echo "${countries[3]}"
```
{% endcode %}

***

## Count the number of elements in an Array

Given a list of countries, each on a new line, your task is to read them into an array and then display the count of elements in that array.

{% code lineNumbers="true" %}
```shell
countries=($(cat))
echo "${#countries[@]}"
```
{% endcode %}

***

## Remove the first capital letter from each element

You are given a list of countries, each on a new line. Your task is to read them into an array and then transform them in the following way:

The first capital letter (if present) in each element of the array should be replaced with a dot ('_._'). Then, display the entire array with a _space_ between each country's names.

{% code lineNumbers="true" %}
```shell
declare -a arr
while read -r line
do
    if [[ $line =~ ^[A-Z] ]]
    then 
        temp=$(echo $line | cut -c 2-)
        arr+=(".${temp}")
    fi
done
echo ${arr[@]}
```
{% endcode %}

***

## Lonely Integer - Bash!

There are N integers in an array A. All but one integer occur in pairs. Your task is to find the number that occurs only once.

**Input Format**

The first line of the input contains an integer N, indicating the number of integers. The next line contains N space-separated integers that form the array A.

{% code lineNumbers="true" %}
```shell
read -r N
read -ra A
echo ${A[@]} | tr " " "\n" | sort | uniq -u
```
{% endcode %}
