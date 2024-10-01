# Introduction

## "Hello World" in C

<figure><img src="../.gitbook/assets/image (175).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="C" %}
```c
#include <stdio.h>

int main() {
    char input[100];
    
    // Read until a new line is received
    scanf("%[^\n]%*c", input);
    
    printf("Hello, World!");
    printf("\n%s", input);
    
    return 0
}
```
{% endtab %}

{% tab title="Rust" %}
```rust
use std::io;

fn main() {
    let mut input: String = String::new();

    io::stdin()
        .read_line(&mut input)
        .expect("Give an Input.");

    println!("Hello, world!");
    println!("{input}")
}
```
{% endtab %}
{% endtabs %}

***

## Playing with Characters

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="C" %}
```c
#include <stdio.h>

int main() {
    char ch;
    char s[100];
    char sen[100];
    
    scanf("%c", &ch);
    scanf("%s", s);
    // Reading the \n from the previous line
    scanf("\n");
    // Reading until a \n is received
    scanf("%[^\n]%*c", sen);
    
    printf("%c", ch);
    printf("\n%s", s);
    printf("\n%s", sen);
    
    return 0
}
```
{% endtab %}

{% tab title="Rust" %}
```rust
use std::io;

fn main() {
    let mut ch: String = String::new();
    let mut s: String = String::new();
    let mut sen: String = String::new();

    io::stdin()
        .read_line(&mut ch)
        .expect("Enter a Character.");

    io::stdin()
        .read_line(&mut s)
        .expect("Enter a Word.");

    io::stdin()
        .read_line(&mut sen)
        .expect("Enter a Sentence");

    print!("{ch}");
    print!("{s}");
    print!("{sen}");
}
```
{% endtab %}
{% endtabs %}

***

## Sum and Difference of Two Numbers

<figure><img src="../.gitbook/assets/image (176).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="C" %}
```c
#include <stdio.h>

int main()
{
	int int_a, int_b;
    float float_a, float_b;
    
    scanf("%d %d", &int_a, &int_b);
    scanf("%f %f", &float_a, &float_b);
    
    printf("%d %d", int_a + int_b, int_a - int_b);
    printf("\n%.1f %.1f", float_a + float_b, float_a - float_b);
    
    return 0;
}
```
{% endtab %}

{% tab title="Rust" %}
```rust
use std::io;

fn main() {
    let mut line1: String = String::new();
    let mut line2: String = String::new();

    io::stdin()
        .read_line(&mut line1)
        .expect("Enter two positive integers.");

    io::stdin()
        .read_line(&mut line2)
        .expect("Enter two positive floating-point numbers.");

    let line1: Vec<isize> = line1.trim()
                                .split_whitespace()
                                .map(|number| number.parse().expect("Expected Integers."))
                                .collect();

    let line2: Vec<f64> = line2.trim()
                            .split_whitespace()
                            .map(|float| float.parse().expect("Expected Floating-Point Numbers."))
                            .collect();

    let int_a = line1[0];
    let int_b = line1[1];
    let float_a = line2[0];
    let float_b = line2[1];

    println!("{} {}", int_a + int_b, int_a - int_b);
    println!("{:.1} {:.1}", float_a + float_b, float_a - float_b);
}
```
{% endtab %}
{% endtabs %}

***

## Functions in C

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="C" %}
```c
#include <stdio.h>

int max_of_four(int a, int b, int c, int d) {
    int max = a;
    
    if (max < b) max = b;
    if (max < c) max = c;
    if (max < d) max = d;
    
    return max;
}


int main() {
    int a, b, c, d;
    scanf("%d %d %d %d", &a, &b, &c, &d);
    int ans = max_of_four(a, b, c, d);
    printf("%d", ans);
    
    return 0;
}
```
{% endtab %}

{% tab title="Rust" %}
```rust
use std::io;

fn max_of_four(a: usize, b: usize, c: usize, d: usize) -> usize {
    let mut max = a;

    if max < b {
        max = b;
    }

    if max < c {
        max = c;
    }

    if max < d {
        max = d;
    }

    max
}

fn main() {
    let mut a: String = String::new();
    let mut b: String = String::new();
    let mut c: String = String::new();
    let mut d: String = String::new();

    io::stdin().read_line(&mut a).expect("Enter the 1st number.");
    let a: usize = a.trim().parse().expect("Expecting a valid 1st number.");

    io::stdin().read_line(&mut b).expect("Enter the 2nd number.");
    let b: usize = b.trim().parse().expect("Expecting a valid 2nd number.");

    io::stdin().read_line(&mut c).expect("Enter the 3rd number.");
    let c: usize = c.trim().parse().expect("Expecting a valid 3rd number.");

    io::stdin().read_line(&mut d).expect("Enter the 4th number.");
    let d: usize = d.trim().parse().expect("Expecting a valid 4th number.");

    let ans = max_of_four(a, b, c, d);

    println!("{ans}");
}
```
{% endtab %}
{% endtabs %}

***

## Pointers in C

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

{% tabs %}
{% tab title="C" %}
```c
#include <stdio.h>

void update(int *a,int *b) {
    int temp = *a;
    *a = *a + *b;
    *b = abs(temp - *b);
}

int main() {
    int a, b;
    int *pa = &a, *pb = &b;
    
    scanf("%d %d", &a, &b);
    update(pa, pb);
    printf("%d\n%d", a, b);

    return 0;
}
```
{% endtab %}

{% tab title="Rust" %}
```rust
use std::io;

fn update(a: &mut isize, b: &mut isize) {
    let temp: isize = *a;
    *a = *a + *b;
    *b = (temp - *b).abs();
}

fn main() {
    let mut a: String = String::new();
    let mut b: String = String::new();

    io::stdin().read_line(&mut a).expect("Failed to read input. Expected a valid number.");
    let mut a: isize = a.trim().parse().expect("Failed to parse input. Expected a valid number.");

    io::stdin().read_line(&mut b).expect("Failed to read input. Expected a valid number.");
    let mut b: isize = b.trim().parse().expect("Failed to parse input. Expected a valid number.");

    update(&mut a, &mut b);

    println!("{a}");
    println!("{b}");
}
```
{% endtab %}
{% endtabs %}
