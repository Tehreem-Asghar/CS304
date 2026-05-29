# 📘 Chapter: const, Initializer List & Static Data Members (Deep Notes)

---

# 🔹 1. const Data Member

## 📌 const kya hota hai?

`const` ka matlab hota hai:

👉 “Ek dafa value set ho gayi to phir change nahi hogi.”

---

## 📌 Class mein const member

```cpp
class Student{
    const int rollNo;
};
```

### 👉 Iska matlab:

- Har student ka `rollNo` fixed hoga
- Baad mein change nahi ho sakta

---

## 📌 Problem samajho

Agar hum try karein:

```cpp
Student::Student(int aNo){
    rollNo = aNo; // ❌ ERROR
}
```

### ❌ Error kyun aata hai?

Kyunkay:

- const member ko assignment se value nahi de sakte
- Woh sirf initialization accept karta hai

---

## 📌 Real Life Example

👉 Roll number = CNIC number jaisa hota hai

- Ek dafa assign ho gaya
- Phir change nahi hota

---

# 🔹 2. Initialization vs Assignment

## 📌 Initialization

👉 Variable banatay waqt value dena

```cpp
int i = 5;
```

---

## 📌 Assignment

👉 Variable banne ke baad value dena

```cpp
int i;
i = 5;
```

---

## 📌 Difference yaad rakho

| Type | Time | Example |
|---|---|---|
| Initialization | Creation time | `int i = 5` |
| Assignment | Later | `i = 5` |

---

## 📌 const problem ka root

👉 const sirf initialization accept karta hai, assignment nahi.

---

# 🔹 3. Member Initializer List

## 📌 Problem

Constructor ke andar const ko assign nahi kar sakte.

---

## 📌 Solution

👉 Initializer list use karo.

---

## 📌 Syntax

```cpp
ClassName(parameters) : member(value)
{
}
```

---

## 📌 Example

```cpp
#include <iostream>
using namespace std;

class Student{
    const int rollNo;
    float GPA;

public:
    Student(int aRollNo)
        : rollNo(aRollNo), GPA(0.0)
    {
        cout << "Roll No: " << rollNo << endl;
        cout << "GPA: " << GPA << endl;
    }
};

int main(){

    Student s1(101);

    return 0;
}
```

---

## 📌 Output

```cpp
Roll No: 101
GPA: 0
```

---

## 📌 Iska matlab

| Member | Value |
|---|---|
| rollNo | Constructor se aayi |
| GPA | Default 0 |

---

## 📌 Real Life Example

👉 Admission system:

- rollNo → fixed
- GPA → start mein 0
- Name → baad mein update ho sakta hai

---

## 📌 Multiple members initialize karna

```cpp
: rollNo(a), GPA(0), name("Unknown")
```

---

# 🔹 4. Important Rule — Initialization Order

## 📌 Rule

👉 Members hamesha class ke order mein initialize hote hain

❌ Initializer list ke order mein nahi

---

## 📌 Example

```cpp
#include <iostream>
using namespace std;

class ABC{

    int x;
    int y;
    int z;

public:

    ABC() : y(10), x(y), z(y)
    {
        cout << "x = " << x << endl;
        cout << "y = " << y << endl;
        cout << "z = " << z << endl;
    }
};

int main(){

    ABC obj;

    return 0;
}
```

---

## 📌 Actual Initialization Order

1. x
2. y
3. z

---

## ❌ Problem

```cpp
x(y)
```

👉 y abhi initialize nahi hua tha

Is liye:

- x = garbage value
- y = 10
- z = 10

---

## 📌 Golden Rule

👉 “Order matters in class, not in initializer list.”

---

# 🔹 5. const Object

## 📌 const object kya hota hai?

Aisa object jiska data change nahi ho sakta.

```cpp
const Student s1;
```

---

## 📌 Rule

✔ Object read-only hota hai  
❌ Data modify nahi kar sakte

---

## 📌 Example Problem

```cpp
const Student s1;

s1.getRollNo(); // ❌ Error
```

---

## 📌 Error kyun aata hai?

Kyunkay normal function object ko change kar sakta hai.

Compiler safe rehna chahta hai.

---

# 🔹 6. const Member Function

## 📌 Definition

Aisa function jo object ko modify na kare.

---

## 📌 Syntax

```cpp
int getRollNo() const;
```

---

## 📌 Correct Example

```cpp
#include <iostream>
using namespace std;

class Student{

    int rollNo;

public:

    Student(int r){
        rollNo = r;
    }

    int getRollNo() const{
        return rollNo;
    }
};

int main(){

    const Student s1(101);

    cout << s1.getRollNo();

    return 0;
}
```

---

## 📌 Output

```cpp
101
```

---

## 📌 Real Life Example

👉 “Sirf dekh sakte ho, change nahi kar sakte.”

---

## 📌 Rule

✔ const object → sirf const function call kar sakta hai

---

# 🔹 7. Static Data Member

## 📌 Definition

Aisa variable jo:

- Class ka hota hai
- Object ka nahi hota

---

## 📌 Simple Meaning

👉 Sab objects is variable ko share karte hain.

---

## 📌 Example

```cpp
class Student{

public:

    static int count;
};
```

---

## 📌 Real Life Example

👉 University total students counter:

- s1 create → count++
- s2 create → count++
- s3 create → count++

👉 Sab same count share karte hain.

---

# 🔹 8. Static Member Memory Behavior

## 📌 Important Points

✔ Sirf 1 copy banti hai  
✔ Sab objects use karte hain  
✔ Memory object ke andar nahi hoti

---

## 📌 Static member define outside class

```cpp
int Student::count = 0;
```

---

## 📌 Complete Example

```cpp
#include <iostream>
using namespace std;

class Student{

public:

    static int count;

    Student(){
        count++;
    }
};

int Student::count = 0;

int main(){

    Student s1;
    Student s2;
    Student s3;

    cout << "Total Students: " << Student::count;

    return 0;
}
```

---

## 📌 Output

```cpp
Total Students: 3
```

---

# 🔹 9. Important Interview / Exam Points

## 📌 const Data Member

✔ Must initialize using initializer list

---

## 📌 const Function

✔ Cannot modify data members

---

## 📌 const Object

✔ Can call only const member functions

---

## 📌 Static Data Member

✔ Shared by all objects  
✔ Single memory location  
✔ Defined outside class

---

# 🔹 FINAL SUMMARY

## 📌 One Line Revision

- `const` → value change nahi hoti
- `initializer list` → constructor se pehle initialization
- `const object` → read-only object
- `const function` → object modify nahi karta
- `static` → shared data among all objects

---

# 🔹 Quick Revision Table

| Concept | Simple Meaning |
|---|---|
| const variable | Change nahi ho sakti |
| Initialization | Creation time value |
| Assignment | Baad mein value dena |
| Initializer List | Constructor se pehle initialize |
| const object | Read-only object |
| const function | Data modify nahi karta |
| static member | Sab objects share karte hain |

---
