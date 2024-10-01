# Conditionals and Loops

## Conditional Statements in C

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="C" %}
```c
#include <assert.h>
#include <limits.h>
#include <math.h>
#include <stdbool.h>
#include <stddef.h>
#include <stdint.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

char* readline();

int main()
{
    char* n_endptr;
    char* n_str = readline();
    int n = strtol(n_str, &n_endptr, 10);

    if (n_endptr == n_str || *n_endptr != '\0') { exit(EXIT_FAILURE); }

    // Write Your Code Here: Start
    if (1 <= n && n <= 9) {
        if (n == 1) printf("one");
        else if (n == 2) printf("two");
        else if (n == 3) printf("three");
        else if (n == 4) printf("four");
        else if (n == 5) printf("five");
        else if (n == 6) printf("six");
        else if (n == 7) printf("seven");
        else if (n == 8) printf("eight");
        else if (n == 9) printf("nine");        
    } else {
        printf("Greater than 9");
    }
    // Write Your Code Here: End

    return 0;
}

char* readline() {
    size_t alloc_length = 1024;
    size_t data_length = 0;
    char* data = malloc(alloc_length);

    while (true) {
        char* cursor = data + data_length;
        char* line = fgets(cursor, alloc_length - data_length, stdin);

        if (!line) { break; }

        data_length += strlen(cursor);

        if (data_length < alloc_length - 1 || data[data_length - 1] == '\n') { break; }

        size_t new_length = alloc_length << 1;
        data = realloc(data, new_length);

        if (!data) { break; }

        alloc_length = new_length;
    }

    if (data[data_length - 1] == '\n') {
        data[data_length - 1] = '\0';
    }

    data = realloc(data, data_length);

    return data;
}
```
{% endtab %}

{% tab title="Rust" %}
```rust
use std::io;

fn main() {
    let mut number: String = String::new();

    io::stdin().read_line(&mut number).expect("Failed to read. Expecting a valid number.");
    let number: isize = number.trim().parse().expect("Expecting a valid number.");

    if 1 <= number && number <= 9 {
        if number == 1 { println!("one"); }
        else if number == 2 { println!("two"); }
        else if number == 3 { println!("three"); }
        else if number == 4 { println!("four"); }
        else if number == 5 { println!("five"); }
        else if number == 6 { println!("six"); }
        else if number == 7 { println!("seven"); }
        else if number == 8 { println!("eight"); }
        else if number == 9 { println!("nine"); }
    }
    else {
        println!("Greather than 9");
    }
}
```
{% endtab %}
{% endtabs %}

***

## For Loop in C

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="C" %}
```c
#include <stdio.h>

int main() 
{
    int a, b;
    scanf("%d\n%d", &a, &b);
  	
    for (int n = a; n <= b; n++ ) {
        if ( 1 <= n && n <= 9 ) {
            if (n == 1) printf("one\n");
            else if (n == 2) printf("two\n");
            else if (n == 3) printf("three\n");
            else if (n == 4) printf("four\n");
            else if (n == 5) printf("five\n");
            else if (n == 6) printf("six\n");
            else if (n == 7) printf("seven\n");
            else if (n == 8) printf("eight\n");
            else if (n == 9) printf("nine\n");        
        }
        else if ( n > 9) {
            if ( n % 2 == 0 ) {
                printf("even\n");
            } else {
                printf("odd\n");
            }
        }
    }

    return 0;
}
```
{% endtab %}

{% tab title="Rust" %}
```rust
use std::io;

fn main() {
    let mut a: String = String::new();
    let mut b: String = String::new();

    io::stdin().read_line(&mut a).expect("Failed to read. Expecting a valid number.");
    let a: isize = a.trim().parse().expect("Expecting a valid number.");

    io::stdin().read_line(&mut b).expect("Faild to read. Expecting a valid number.");
    let b: isize = b.trim().parse().expect("Expecting a valid number.");

    for number in a..=b {
        println!("{number}");
        if 1 <= number && number <= 9 {
            if number == 1 { println!("one"); }
            else if number == 2 { println!("two"); }
            else if number == 3 { println!("three"); }
            else if number == 4 { println!("four"); }
            else if number == 5 { println!("five"); }
            else if number == 6 { println!("six"); }
            else if number == 7 { println!("seven"); }
            else if number == 8 { println!("eight"); }
            else if number == 9 { println!("nine"); }
        }
        else if number > 9 {
            if number % 2 == 0 { println!("even"); }
            else { println!("odd"); }
        }
    }
}
```
{% endtab %}
{% endtabs %}

***

## Sum of Digits of a Five Digit Number

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="C" %}
```cpp
#include <stdio.h>

int main() {
    int n;
    scanf("%d", &n);
    
    int _, sum = 0;
    
    for (_; _ < 5; _++) {
        // Adding the last digit to sum
        sum += n % 10;
        
        // Removing the last digit
        n /= 10;
    }
    
    printf("%d", sum);
    
    return 0;
}
```
{% endtab %}

{% tab title="Rust" %}
```rust
use std::io;

fn main() {
    let mut number: String = String::new();
    let mut _sum: isize = 0;

    io::stdin().read_line(&mut number).expect("Failed to read. Expecting a valid number.");
    let mut number: isize = number.trim().parse().expect("Expecting a valid number.");

    for _ in 0..5 {
        // Adding the last digit to _sum
        _sum += number % 10;
        
        // Removing the last digit
        number /= 10;
    }

    println!("{_sum}");
}
```
{% endtab %}
{% endtabs %}

***

## Bitwise Operators

<figure><img src="../.gitbook/assets/image (178).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="C" %}
```c
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

//Complete the following function.
void calculate_the_maximum(int n, int k) {
  int and_max = 0;
  int or_max = 0;
  int xor_max = 0;
  
  for ( int a = 1; a <= n; a++) {
      for (int b = a + 1; b <= n; b++ ) {
          int a_and_b = a & b;
          int a_or_b = a | b;
          int a_xor_b = a ^ b;
          
          if (a_and_b < k && a_and_b > and_max) and_max = a_and_b;
          if (a_or_b < k && a_or_b > or_max) or_max = a_or_b;
          if (a_xor_b < k && a_xor_b > xor_max) xor_max = a_xor_b;
      }
  }
  
  printf("%d\n", and_max);
  printf("%d\n", or_max);
  printf("%d\n", xor_max);
}

int main() {
    int n, k;
  
    scanf("%d %d", &n, &k);
    calculate_the_maximum(n, k);
 
    return 0;
}
```
{% endtab %}

{% tab title="Rust" %}
```rust
use std::io;

fn calculate_the_maximum(n: isize, k: isize) {
    let mut and_max = 0;
    let mut or_max = 0;
    let mut xor_max = 0;

    for a in 1..=n {
        for b in (a + 1)..=n {
            let a_and_b = a & b;
            let a_or_b = a | b;
            let a_xor_b = a ^ b;

            if a_and_b < k && a_and_b > and_max { and_max = a_and_b; }
            if a_or_b < k && a_or_b > or_max { or_max = a_or_b; }
            if a_xor_b < k && a_xor_b > xor_max { xor_max = a_xor_b; }
        }
    }
    
    print!("{and_max}\n{or_max}\n{xor_max}\n");
}

fn main() {
    let mut input_line: String = String::new();

    io::stdin()
        .read_line(&mut input_line)
        .expect("Failed to read. Expecting two valid Integers Separated by a space.");

    let inputs: Vec<isize> = input_line.trim()
                        .split_whitespace()
                        .map(|number| number.parse()
                                            .expect("Expecting a valid integer.")
                            )
                        .collect();

    calculate_the_maximum(inputs[0], inputs[1]);
}
```
{% endtab %}
{% endtabs %}

***

## Printing Pattern Using Loops

<figure><img src="../.gitbook/assets/image (177).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="C" %}
```c
#include <stdio.h>

void print_pattern(int n, int row) {
    // Print decreasing part
    for (int val = n; val > row; val--) {
        printf("%d ", val);
    }

    // Print middle repeating part
    int middle_count = (row - 1) * 2 + 1;
    for (int j = 0; j < middle_count; j++) {
        printf("%d ", row);
    }

    // Print increasing part
    for (int val = row + 1; val <= n; val++) {
        printf("%d ", val);
    }

    printf("\n");
}

int main() {
    int n;
    scanf("%d", &n);

    // Print top half (and middle row)
    for (int row = n; row >= 1; row--) {
        print_pattern(n, row);
    }

    // Print bottom half
    for (int row = 2; row <= n; row++) {
        print_pattern(n, row);
    }

    return 0;
}
```
{% endtab %}

{% tab title="Rust" %}
```rust
use std::io;

fn print_pattern(n: isize, row: isize) {
    // Print decreasing part
    for val in (row..=n).rev() {
        print!("{val} ");
    }

    // Print middle repeating part
    let middle_count = (row - 1) * 2 + 1;
    for _ in 1..middle_count {
        print!("{row} ");
    }

    // Print increasing part
    for val in (row + 1)..=n {
        print!("{val} ");
    }

    println!();
}

fn main() {
    let mut n: String = String::new();

    io::stdin().read_line(&mut n).expect("Failed to read. Expecting a valid number");
    let n: isize = n.trim().parse().expect("Expecting a valid number");

    for row in (1..=n).rev() {
        // println!("{}", row);
        print_pattern(n, row)
    }

    for row in 2..=n {
        print_pattern(n, row)
    }
}
```
{% endtab %}
{% endtabs %}
