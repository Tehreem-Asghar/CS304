# Lecture No. 19 — Overloading Stream Insertion & Extraction Operators in C++

# Introduction

C++ mein hum data ko screen par display karne aur user se input lene ke liye streams use karte hain.

Do important operators hain:

| Operator | Name | Purpose |
|---|---|---|
| `<<` | Stream Insertion Operator | Output display karna |
| `>>` | Stream Extraction Operator | Input lena |

---

# 19.1 Stream Insertion Operator (`<<`)

Ye operator data ko output stream mein bhejne ke liye use hota hai.

Default output stream:

```cpp
cout
```

Ye console screen par output show karta hai.

---

# Simple Example

```cpp
#include <iostream>
using namespace std;

int main() {

    int i = 1;
    int j = 2;

    cout << "i = " << i << endl;
    cout << "j = " << j << endl;

    return 0;
}
```

---

# Output

```cpp
i = 1
j = 2
```

---

# Real-Life Example

Socho `cout` ek delivery boy hai.

Aur `<<` operator parcel bhejne ka kaam karta hai.

```cpp
cout << data;
```

Matlab:

"Ye data screen tak pohcha do."

---

# 19.2 Stream Extraction Operator (`>>`)

Ye operator input stream se data lene ke liye use hota hai.

Default input stream:

```cpp
cin
```

---

# Simple Example

```cpp
#include <iostream>
using namespace std;

int main() {

    int age;

    cout << "Enter your age: ";

    cin >> age;

    cout << "Your age is: " << age;

    return 0;
}
```

---

# Output

```cpp
Enter your age: 20
Your age is: 20
```

---

# Real-Life Example

Socho `cin` ek collector hai.

Aur `>>` operator user se data lekar variable mein store karta hai.

```cpp
cin >> age;
```

Matlab:

"User se value lo aur age mein store kar do."

---

# Behind the Scene Working

Jab hum likhte hain:

```cpp
cout << i;
```

Asal mein compiler ye function call karta hai:

```cpp
operator<<(cout, i);
```

---

# Similarly

```cpp
cin >> i;
```

Actually:

```cpp
operator>>(cin, i);
```

---

# Cascading Statements

C++ multiple outputs/input ek hi line mein allow karta hai.

---

# Example

```cpp
cout << "Hello " << "World";
```

---

# Input Example

```cpp
cin >> a >> b;
```

---

# Why Cascading Works?

Kyuki operators stream ka reference return karte hain.

---

# User Defined Classes Problem

Basic data types ke liye operators already overloaded hote hain.

Lekin user-defined classes ke liye nahi.

---

# Example

```cpp
class Complex {

};
```

```cpp
Complex c1;

cout << c1;
```

---

# Compiler Error

Compiler nahi samjhega ke `Complex` object ko print kaise karna hai.

Isliye hume manually operator overload karna padega.

---

# Complex Number Class

Complex number:

```cpp
(Real Part, Imaginary Part)
```

Example:

```cpp
(3, 4)
```

Yahan:

- 3 → Real Part
- 4 → Imaginary Part

---

# 19.3 Overloading Stream Insertion Operator (`<<`)

---

# Wrong Approach (Member Function)

```cpp
class Complex {

public:

    void operator<<(ostream&);
};
```

---

# Problem

Use kuch aise hoga:

```cpp
c1 << cout;
```

Ye confusing syntax hai.

Aur cascading bhi work nahi karegi.

---

# Correct Approach → Friend Function

Stream operators ko friend function banana best practice hai.

---

# Complex Class

```cpp
#include <iostream>
using namespace std;

class Complex {

private:

    float real;
    float img;

public:

    Complex(float r = 0, float i = 0) {

        real = r;
        img = i;
    }

    friend ostream& operator<<(ostream& os, const Complex& c);
};
```

---

# Stream Insertion Operator Code

```cpp
ostream& operator<<(ostream& os, const Complex& c) {

    os << "(" << c.real << ", " << c.img << ")";

    return os;
}
```

---

# Explanation

## `ostream& os`

Output stream object receive karega.

Usually:

```cpp
cout
```

---

## `const Complex& c`

Complex object receive karega.

Const isliye use kiya kyuki hum sirf data read kar rahe hain.

---

## `return os`

Cascading statements allow karne ke liye.

---

# Complete Program

```cpp
#include <iostream>
using namespace std;

class Complex {

private:

    float real;
    float img;

public:

    Complex(float r = 0, float i = 0) {

        real = r;
        img = i;
    }

    friend ostream& operator<<(ostream& os, const Complex& c);
};

ostream& operator<<(ostream& os, const Complex& c) {

    os << "(" << c.real << ", " << c.img << ")";

    return os;
}

int main() {

    Complex c1(1.5, 2.5);
    Complex c2(4.2, 8.1);

    cout << c1 << endl;
    cout << c2;

    return 0;
}
```

---

# Output

```cpp
(1.5, 2.5)
(4.2, 8.1)
```

---

# Cascading Example

```cpp
cout << c1 << c2;
```

Actually:

```cpp
operator<<( operator<<(cout, c1), c2 );
```

---

# Real-Life Understanding

Socho:

```cpp
cout
```

Ek pipeline hai.

Har `<<` next data us pipeline mein bhejta jata hai.

---

# 19.4 Overloading Stream Extraction Operator (`>>`)

Ab hum user se Complex object ka input lena chahte hain.

---

# Complex Class

```cpp
class Complex {

private:

    float real;
    float img;

public:

    friend istream& operator>>(istream& in, Complex& c);
};
```

---

# Stream Extraction Operator Code

```cpp
istream& operator>>(istream& in, Complex& c) {

    in >> c.real;
    in >> c.img;

    return in;
}
```

---

# Important Point

Yahan `Complex` object const nahi hoga.

Kyuki values change ho rahi hain.

---

# Complete Program

```cpp
#include <iostream>
using namespace std;

class Complex {

private:

    float real;
    float img;

public:

    friend istream& operator>>(istream& in, Complex& c);

    friend ostream& operator<<(ostream& os, const Complex& c);
};

istream& operator>>(istream& in, Complex& c) {

    in >> c.real;
    in >> c.img;

    return in;
}

ostream& operator<<(ostream& os, const Complex& c) {

    os << "(" << c.real << ", " << c.img << ")";

    return os;
}

int main() {

    Complex c1;

    cout << "Enter real and imaginary values: ";

    cin >> c1;

    cout << "Complex Number: " << c1;

    return 0;
}
```

---

# Input

```cpp
5.5 7.2
```

---

# Output

```cpp
Complex Number: (5.5, 7.2)
```

---

# Real-Life Example

Socho:

```cpp
cin >> c1;
```

Matlab:

"User se values lo aur Complex object mein bhar do."

---

# Difference Between `<<` and `>>`

| Operator | Direction | Purpose |
|---|---|---|
| `<<` | Program → Screen | Output |
| `>>` | User → Program | Input |

---

# Why Stream Operators are Friend Functions?

Kyuki left side par:

```cpp
cout
```

ya:

```cpp
cin
```

hota hai.

Agar member function hota to left object `Complex` hona chahiye tha.

Lekin actual syntax:

```cpp
cout << c1;
```

hai.

Isliye non-member friend function best choice hai.

---

# Equality Operator (`==`)

Ye check karta hai ke do objects equal hain ya nahi.

---

# Example

```cpp
class Complex {

private:

    float real;
    float img;

public:

    Complex(float r = 0, float i = 0) {

        real = r;
        img = i;
    }

    bool operator==(const Complex& c);
};
```

---

# Equality Operator Code

```cpp
bool Complex::operator==(const Complex& c) {

    if ((real == c.real) &&
        (img == c.img)) {

        return true;
    }

    else {

        return false;
    }
}
```

---

# Complete Example

```cpp
#include <iostream>
using namespace std;

class Complex {

private:

    float real;
    float img;

public:

    Complex(float r = 0, float i = 0) {

        real = r;
        img = i;
    }

    bool operator==(const Complex& c);
};

bool Complex::operator==(const Complex& c) {

    if ((real == c.real) &&
        (img == c.img)) {

        return true;
    }

    return false;
}

int main() {

    Complex c1(2, 3);
    Complex c2(2, 3);

    if (c1 == c2) {

        cout << "Objects are equal";
    }

    else {

        cout << "Objects are not equal";
    }

    return 0;
}
```

---

# Output

```cpp
Objects are equal
```

---

# Inequality Operator (`!=`)

Ye check karta hai ke objects different hain ya nahi.

---

# Code

```cpp
bool Complex::operator!=(const Complex& c) {

    if ((real != c.real) ||
        (img != c.img)) {

        return true;
    }

    return false;
}
```

---

# Complete Example

```cpp
#include <iostream>
using namespace std;

class Complex {

private:

    float real;
    float img;

public:

    Complex(float r = 0, float i = 0) {

        real = r;
        img = i;
    }

    bool operator!=(const Complex& c);
};

bool Complex::operator!=(const Complex& c) {

    if ((real != c.real) ||
        (img != c.img)) {

        return true;
    }

    return false;
}

int main() {

    Complex c1(2, 3);
    Complex c2(5, 7);

    if (c1 != c2) {

        cout << "Objects are different";
    }

    else {

        cout << "Objects are same";
    }

    return 0;
}
```

---

# Output

```cpp
Objects are different
```

---

# Important Concepts Summary

| Concept | Explanation |
|---|---|
| `<<` | Output operator |
| `>>` | Input operator |
| `ostream` | Output stream class |
| `istream` | Input stream class |
| Friend Function | Stream operators ke liye best |
| Cascading | Multiple operators ek line mein |
| `return os` | Cascading enable karta hai |
| `const Complex&` | Object sirf read karna |
| `Complex&` | Object modify karna |

---

# Real-Life Analogy

| Programming Concept | Real-Life Example |
|---|---|
| `cout` | Delivery system |
| `cin` | Data collector |
| `<<` | Parcel bhejna |
| `>>` | Parcel receive karna |
| Stream | Pipe jisme data flow hota hai |

---

# Final Summary

Lecture 19 mein humne seekha:

- Stream insertion operator (`<<`)
- Stream extraction operator (`>>`)
- Operator overloading for user-defined classes
- Friend functions
- Cascading statements
- Equality (`==`) operator
- Inequality (`!=`) operator

Ye concepts C++ OOP mein bohat important hain aur real software applications mein extensively use hote hain.
