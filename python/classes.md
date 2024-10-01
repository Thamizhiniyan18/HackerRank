# Classes

{% embed url="https://www.hackerrank.com/domains/python?badge_type=python&filters%5Bsubdomains%5D%5B%5D=py-classes" %}

## Class 2 - Find the Torsional Angle

<figure><img src="../.gitbook/assets/image (172).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import math


class Points(object):
    def __init__(self, x, y, z):
        self.x = x
        self.y = y
        self.z = z

    def __sub__(self, no):
        return Points(self.x - no.x, self.y - no.y, self.z - no.z)

    def dot(self, no):
        return (self.x * no.x) + (self.y * no.y) + (self.z * no.z)

    def cross(self, no):
        return Points((self.y * no.z) - (self.z * no.y), (self.z * no.x) - (self.x * no.z),
                      (self.x * no.y) - (self.y * no.x))

    def absolute(self):
        return pow((self.x ** 2 + self.y ** 2 + self.z ** 2), 0.5)


if __name__ == '__main__':
    points = list()
    for i in range(4):
        a = list(map(float, input().split()))
        points.append(a)

    a, b, c, d = Points(*points[0]), Points(*points[1]), Points(*points[2]), Points(*points[3])
    x = (b - a).cross(c - b)
    y = (c - b).cross(d - c)
    angle = math.acos(x.dot(y) / (x.absolute() * y.absolute()))

    print("%.2f" % math.degrees(angle))
```
{% endcode %}

***

## Classes: Dealing with Complex Numbers

<figure><img src="../.gitbook/assets/image (173).png" alt=""><figcaption></figcaption></figure>

{% code lineNumbers="true" %}
```python
import math

class Complex(object):
    def __init__(self, real, imaginary):
        self.r = real
        self.i = imaginary
        
    def __add__(self, no):
        return Complex(self.r + no.r, self.i + no.i)
        
    def __sub__(self, no):
        return Complex(self.r - no.r, self.i - no.i)
        
    def __mul__(self, no):
        return Complex((self.r * no.r) - (self.i * no.i), (self.r * no.i) + (self.i * no.r))

    def __truediv__(self, no):
        n1 = (self.r * no.r) + (self.i * no.i.conjugate())
        n2 = (self.i * no.r) - (self.r * no.i.conjugate())
        d = pow(no.r, 2) + pow(no.i, 2)
        return Complex(n1 / d, n2 / d)

    def mod(self):
        modulus = pow(self.r, 2) + pow(self.i, 2)
        return Complex(pow(modulus, 0.5), 0)

    def __str__(self):
        if self.i == 0:
            result = "%.2f+0.00i" % (self.r)
        elif self.r == 0:
            if self.i >= 0:
                result = "0.00+%.2fi" % (self.i)
            else:
                result = "0.00-%.2fi" % (abs(self.i))
        elif self.i > 0:
            result = "%.2f+%.2fi" % (self.r, self.i)
        else:
            result = "%.2f-%.2fi" % (self.r, abs(self.i))
        return result

if __name__ == '__main__':
    c = map(float, input().split())
    d = map(float, input().split())
    x = Complex(*c)
    y = Complex(*d)
    print(*map(str, [x+y, x-y, x*y, x/y, x.mod(), y.mod()]), sep='\n')
```
{% endcode %}
