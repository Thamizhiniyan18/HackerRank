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

```shell
countries=($(cat))
filtered=(${countries[@]/*[Aa]*/})
echo "${filtered[@]}"
```

### Method 2

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

***
