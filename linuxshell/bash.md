# Bash

{% embed url="https://www.hackerrank.com/domains/shell?filters%5Bsubdomains%5D%5B%5D=bash" %}
Link to this challege section
{% endembed %}

## Let's Echo

Write a bash script that prints the string "HELLO".

```bash
echo HELLO
```

***

## Looping and Skipping

Your task is to use _for_ loops to display only _odd_ natural numbers from 1 to 99 .&#x20;

```bash
for i in {1..99}; do if [[ $((i % 2)) -eq 1 ]]; then echo $i; fi; done
```

***

## A Personalized Echo

Write a Bash script which accepts as input and displays the greeting "Welcome (name)".

```bash
read -r name; echo Welcome $name
```

***

## Looping with Numbers

Use a _for_ loop to display the natural numbers from  1 to 50.

```bash
for i in {1..50}; do echo $i; done
```

***

## The World of Numbers

Given two integers, and , find their sum, difference, product, and quotient.

{% code lineNumbers="true" %}
```bash
read -r a
read -r b

echo $((a + b))
echo $((a - b))
echo $((a * b))
echo $((a / b))
```
{% endcode %}

***

## Comparing Numbers

Given two integers,  X and Y , identify whether X < Y  or X > Y  or X = Y.

Exactly one of the following lines:\
\- _X is less than Y_\
\- _X is greater than Y_\
\- _X is equal to Y_

{% code lineNumbers="true" %}
```bash
read -r X
read -r Y

if [[ X -lt Y ]]; then echo X is less than Y; fi
if [[ X -gt Y ]]; then echo X is greater than Y; fi
if [[ X -eq Y ]]; then echo X is equal to Y; fi
```
{% endcode %}

***

## Getting Started with Conditionals

Read in one character from STDIN. If the character is 'Y' or 'y' display "YES". If the character is 'N' or 'n' display "NO". No other character will be provided as input.

{% code lineNumbers="true" %}
```bash
read -r input;

if [[ $input == "y" || $input == "Y" ]]; then echo YES; fi;
if [[ $input == "n" || $input == "N" ]]; then echo NO; fi;
```
{% endcode %}

***

## More On Conditionals

Given three integers (, , and ) representing the three sides of a triangle, identify whether the triangle is scalene, isosceles, or equilateral.

* If all three sides are equal, output `EQUILATERAL`.
* Otherwise, if any two sides are equal, output `ISOSCELES`.
* Otherwise, output `SCALENE`.

{% code lineNumbers="true" %}
```bash
read -r X;
read -r Y;
read -r Z;

if [[ $X -eq $Y && $Y -eq $Z ]]; then echo EQUILATERAL; fi;
if [[ $X -ne $Y && $Y -ne $Z ]]; then echo SCALENE; fi;
if [[ $X -eq $Y && $Y -ne $Z || $Y -eq $Z && $Z -ne $X || $Z == $X && $X -ne $Y ]]; then echo ISOSCELES; fi;
```
{% endcode %}

***

## Arithmetic Operations

A mathematical expression containing +,-,\*,^, / and parenthesis will be provided. Read in the expression, then evaluate it. Display the result rounded to  decimal places.

{% code lineNumbers="true" %}
```bash
read -r exp
printf %.3f $(echo "$exp" | bc -l)
```
{% endcode %}

***

## Compute the Average

Given N  integers, compute their average, rounded to three decimal places.

{% code lineNumbers="true" %}
```bash
read -r N
declare -i total

for ((i = 0; i < $N; i++)); do
  read -r temp
  ((total += temp))
done

printf %.3f $(echo "$total / $N" | bc -l)
```
{% endcode %}

***

## Functions and Fractals - Recursive Trees - Bash!

This challenge involves the construction of trees, in the form of ASCII Art.

We have to deal with real world constraints, so we cannot keep repeating the pattern infinitely. So, we will provide you a number of iterations, and you need to generate the ASCII version of the Fractal Tree for only those many iterations (or, levels of recursion).

{% code lineNumbers="true" %}
```shell
declare -A matrix


grid()
{
    for(( i=0; i < $1; i++ )) do
    
        for(( j=0; j<$2; j++ )); do 
        
            matrix[$i,$j]="_"  
        
        done
        
    done
}

print()
{
    for(( i=0; i < $1; i++ )) do
    
        for(( j=0; j<$2; j++ )); do
         
            printf "%s" ${matrix[$i,$j]} 
        
        done
        
        printf "\n"
        
    done
}

fractal()
{
    local r=$1 
    local c=$2    
    local itr=$3 
    local depth=$(($4 - 1))
    
    if (( depth == 0 )); then 
        return 0; 
    fi
    
    #make the trunk
    for(( i=0; i<$itr; i++ )); do 
        matrix[$(($r - $i)),$c]="1" 
    done
            
    #left diagonal
    for(( i=0; i<$itr; i++ )); do 
        matrix[$(($r - $itr - $i)),$(($c - $i - 1))]="1"; 
    done  
      
    #right diagonal
    for(( i=0; i<$itr; i++ )); do 
        matrix[$(($r - $itr - $i)),$(($c + $i + 1))]="1"; 
    done 
       
    #make Y in left diagonal
    fractal $(($r - 2 * $itr)) $(($c - $itr)) $(($itr / 2)) $depth 
    
    #make Y in right diagonal  
    fractal $(($r - 2 * $itr)) $(($c + $itr)) $(($itr / 2)) $depth 
       
}

main()
{

    ROWS=63 
    COLS=100

    grid $ROWS $COLS

    read depth
    
    fractal 62 49 16 $(($depth + 1))

    print $ROWS $COLS
    
}

main
```
{% endcode %}
