# Closures and Decorators

## Standardize Mobile Number Using Decorators

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

```python
def wrapper(f):
    def fun(l):
        return f(f'+91 {each[-10:-5]} {each[-5:]}' for each in l)

    return fun


@wrapper
def sort_phone(l):
    print(*sorted(l), sep='\n')


if __name__ == '__main__':
    l = [input() for _ in range(int(input()))]
    sort_phone(l)
```

***

## Decorators 2 - Name Directory

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

```python
def person_lister(f):
    def inner(people):
        return [f(each) for each in sorted(people, key=lambda x: int(x[2]))]

    return inner


@person_lister
def name_format(person):
    return ("Mr. " if person[3] == "M" else "Ms. ") + person[0] + " " + person[1]


if __name__ == '__main__':
    people = [input().split() for i in range(int(input()))]
    print(*name_format(people), sep='\n')
```
