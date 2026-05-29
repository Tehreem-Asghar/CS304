# Chapter 07 — Object Oriented Programming (C++)

## 📌 07.1 Class

Object Oriented Programming (OOP) ka basic idea **objects** hota hai, aur programming languages mein objects ko implement karne ke liye **classes** use hoti hain.

### 🔹 Class kya hai?
Class C++ ka ek mechanism hai jo real-world objects ko program mein represent karta hai.

👉 Class ek **user-defined data type** hota hai jo:
- attributes (data)
- behaviours (functions)

ko combine karta hai.

---

## 🌍 Real Life Example

### 🦁 Lion Example
Har lion:
- Color
- Age
- Weight

Behaviours:
- Roar
- Hunt
- Run

---

### 🎓 Student Example

Har student:
- Name
- Roll No
- Class

Behaviours:
- Study
- Register
- Attend class

---

## 🏫 Real World System Example

University system mein:
- Student
- Teacher
- Subject
- Classroom

Yeh sab objects hain jo ek dusre se interact karte hain.

👉 Example:
Student teacher se service leta hai → teaching

---

## 📌 07.2 Type in C++

C++ mein built-in types hotay hain:
- int
- float
- char

Lekin **student jaisa type built-in nahi hota**.

👉 Is liye hum **class use karke user-defined type banate hain**

### Example:
- Student (student management system)
- Circle (drawing software)

---

## 📌 Class Structure

```cpp
class Student {
    // data members
    // member functions
};
```

---

## 📌 07.3 Abstraction

### 🔹 Abstraction kya hai?

Abstraction ka matlab:
👉 sirf necessary information show karna  
👉 irrelevant details hide karna  

---

## 🎓 Student Example

### Included (Important):
- Name
- Address

### Not Included (Irrelevant):
- Sibling
- Father Business

👉 System ke liye jo cheez useful nahi hoti wo ignore kar di jati hai.

---

## 📌 07.4 User Defined Types

C++ mein 2 ways:

### 1️⃣ Structure

```cpp
struct Student {
    int rollNo;
    char name[20];
};
```

👉 C++ mein struct ke andar functions bhi ho sakte hain.

---

### 2️⃣ Class

```cpp
class Student {
private:
    int rollNo;
    char *name;
    float CGPA;

public:
    void setName(char *);
    void setRollNo(int);
};
```

---

## 📌 Why Member Functions?

### 1. Behaviour model karti hain
Object ka behaviour define hota hai.

### 2. Data Hiding
Data ko direct access se protect karti hain.

### 3. Validation (Important)

```cpp
void setRollNo(int r) {
    if (r > 0)
        rollNo = r;
}
```

---

## ❌ Wrong Example

```cpp
aStudent.rollNo = -5;
```

## ✅ Correct Way

```cpp
aStudent.setRollNo(5);
```

---

## 📌 07.5 Object and Class

### 🔹 Object kya hai?
Object class ka **instance (copy)** hota hai.

### Example:

```cpp
Student aStudent;
Student bStudent;
```

---

## 📌 07.6 Accessing Members

### 1️⃣ Dot Operator (.)

```cpp
Student s;
s.rollNo = 5;
```

---

### 2️⃣ Arrow Operator (->)

```cpp
Student *s = new Student();
s->rollNo = 5;
```

---

## ⚠️ Important Note

Direct access OOP principle ke against hai.

👉 Best practice:
- setters
- getters

---

## 📌 07.7 Access Specifiers

### 1️⃣ public
✔ outside class access allowed

### 2️⃣ private
❌ only class ke andar access

### 3️⃣ protected
👉 inheritance mein use hota hai

---

## 🎓 Example

```cpp
class Student {
private:
    char *name;
    int rollNo;

public:
    void setName(char *);
    void setRollNo(int);
};
```

---

## 📌 Setter Example

```cpp
void Student::setRollNo(int r) {
    if (r > 0)
        rollNo = r;
}
```

---

## 📌 Main Function Example

```cpp
int main() {
    Student aStudent;

    aStudent.setRollNo(10);
    aStudent.setName("Ali");
}
```

---

## ❌ Wrong Access

```cpp
aStudent.rollNo = 5;   // error (private)
```

---

## 📌 Default Access Specifier

Agar kuch mention na ho to:

👉 default = private

---

## 📌 Final Summary

✔ Class = blueprint of object  
✔ Object = instance of class  
✔ Abstraction = unnecessary details hide karna  
✔ Encapsulation = data + functions + protection  
✔ Access Specifiers = control access  
✔ Setters/Getters = safe access method  

---

## 🌍 Real Life Analogy

| Concept | Real Life Example |
|----------|------------------|
| Class | Blueprint of car |
| Object | Actual car |
| Private | Car engine (hidden) |
| Public | Steering, brakes |
| Setter | Mechanic adjusting settings |

---
