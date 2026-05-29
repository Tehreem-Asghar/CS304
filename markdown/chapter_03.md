# 📘 Lecture No. 03

## 📚 Lecture Contents

- Abstraction  
- Classes  
- Inheritance  
- Inheritance ke major benefits (Reuse)  

---

# 🔹 03.1 Abstraction

Real life objects ke paas bohat saare **attributes (khasoosiyat)** aur **behaviors (kaam)** hote hain, lekin aksar hum sirf un cheezon mein interested hote hain jo humare **current problem se related** hoti hain.

## 📌 Example

Agar hum **school system** bana rahe hain, to hume **student** ya **teacher** ki personal life se koi lena dena nahi hota, kyun ke us ka system par koi effect nahi hota.

Is liye hum objects ko sirf **school system ke perspective** se dekhte hain aur baqi **unnecessary cheezon ko ignore** kar dete hain.

👉 Is concept ko **“Abstraction”** kehte hain.

---

## 🔹 Abstraction kya karti hai?

Abstraction complexity (**mushkilat**) ko handle karne ka tareeqa hai aur cheezon ko **simple** banati hai.

---

## 🔹 Principle of Abstraction

👉 **“Sirf un details ko capture karo jo current problem ke liye zaroori hain”**

---

## 🔹 Abstraction Example

Maan lo hume yeh statement implement karni hai:

👉 **“Ali ek PhD student hai aur BS students ko parhata hai”**

Yahan **Ali object** ke 2 perspectives hain:

1. Student perspective  
2. Teacher perspective  

---

## 🔹 Ali ke Attributes

- Name  
- Age  
- Student Roll No  
- Year of Study  
- CGPA  
- Employee ID  
- Designation  
- Salary  

---

## 🔹 Explanation

Jaise ke aap dekh sakte ho:

👉 Kuch attributes **student perspective** se related hain:

- Roll No  
- CGPA  
- Year of Study  

👉 Aur kuch attributes **teacher perspective** se related hain:

- Employee ID  
- Designation  
- Salary  

---

## 🔹 Conclusion (Simple Words)

Abstraction ka matlab hai:

👉 **“Har situation ke hisaab se sirf relevant cheezon ko use karo, baqi sab ignore kar do”**

## 🔹 Ali ka Behavior (Functions / Kaam)

Isi tarah hum Ali ke behavior ko bhi summarize kar sakte hain:

- Study (parhna)  
- DevelopExam (paper banana)  
- GiveExam (paper dena)  
- TakeExam (paper lena)  
- PlaySports (khelna)  
- Eat (khana)  
- DeliverLecture (lecture dena)  
- Walk (chalna)  

---

## 🔹 Explanation

Jaise attributes ko divide kiya tha, waise hi Ali ke behaviors bhi 2 perspectives mein divide ho sakte hain:

---

## 🎓 Student Perspective

### 📌 Attributes

- Name  
- Student Roll No  
- Year of Study  
- CGPA  
- Age  

### ⚙️ Behaviour

- Study  
- GiveExam  
- PlaySports  
- Eat  
- Walk  

---

## 👨‍🏫 Teacher Perspective

### 📌 Attributes

- Name  
- Employee ID  
- Designation  
- Salary  
- Age  

### ⚙️ Behaviour

- DevelopExam  
- TakeExam  
- DeliverLecture  

---

## 🔹 Different Perspectives Examples

### 🐱 Cat (Billi) Example

👉 **Ordinary Perspective:**

- 4 legs  
- Tail  

👉 **Surgeon Perspective:**

- Skeleton  
- Heart  
- 2 ears  
- Sharp teeth  
- Kidney  
- Stomach  

---

### 🚗 Car Example

👉 **Driver’s View:**

Car chalane ke liye simple controls (steering, brake, etc.)

👉 **Engineer’s View:**

Engine, parts, internal system  

---

## 🔹 Abstraction ke Advantages

1. Yeh unnecessary details ko hide karta hai aur problem ko samajhna easy banata hai  
2. Sirf ek perspective par focus karne se baqi cheezon ki implementation baad mein change kar sakte hain  

👉 Encapsulation ki tarah, abstraction bhi **information hiding** ke liye use hoti hai  
(yaani sirf relevant info dikhana, baqi hide karna)

---

# 📘 03.2 Classes

OOP mein hum har type ke objects ke liye ek **general sketch (blueprint)** banate hain.

👉 Isi sketch ko **Class** kehte hain  

Phir hum us class se multiple objects (instances) banate hain.

---

## 🔹 Important Point

Same type ke objects ke:

- ✔ Same structure hota hai  
- ✔ Same behavior hota hai  
- ❌ Lekin data different hota hai  

---

## 🔹 Class Example 1

- Ali studies mathematics  
- Anam studies physics  
- Sohail studies chemistry  

👉 Yeh sab **Student class ke instances** hain  

---

## 🔹 Class Example 2

- Ahsan teaches mathematics  
- Aamir teaches computer science  
- Atif teaches physics  

👉 Yeh sab **Teacher class ke instances** hain  

---

## 🔹 Class Representation

Class ko rectangle se represent karte hain:

- Class Name  
- Attributes  
- Operations (Functions)  

---

# 🔹 03.3 Inheritance

Real life mein:

👉 Bachay apne parents ki qualities inherit karte hain  

Isi tarah OOP mein bhi:

👉 Ek class doosri class se properties inherit kar sakti hai  

---

## 🔹 Definition

Agar class B, class A se inherit kare:

👉 To B ke paas A ki sari properties aur behavior honge  

---

## 🔹 Important Terms

- Parent Class = Base Class  
- Child Class = Derived Class  

👉 Derived class apni extra properties bhi rakh sakti hai  

---

## 🔹 “IS A” Relationship

👉 Yeh inheritance ko represent karta hai  

### 📌 Examples

- Student **IS A** Person  
- Teacher **IS A** Person  
- Doctor **IS A** Person  

- Circle **IS A** Shape  
- Line **IS A** Shape  
- Triangle **IS A** Shape  

---

## 🔹 Inheritance Structure (Simple)

### 👤 Person

- name  
- age  
- gender  
- eat()  
- walk()  

---

### 👨‍🏫 Teacher

- designation  
- salary  
- teach()  
- takeExam()  

---

### 🎓 Student

- program  
- studyYear  
- study()  
- heldExam()  

---

### 🩺 Doctor

- designation  
- salary  
- checkUp()  
- prescribe()  

---

## 🔹 Shapes Example

### 🔷 Shape

- color  
- coord  
- draw()  
- rotate()  
- setColor()  

---

### ⚪ Circle

- radius  
- draw()  
- computeArea()  

---

### 📏 Line

- length  
- draw()  

---

### 🔺 Triangle

- angle  
- draw()  
- computeArea()  

---

## 🔹 Inheritance ke Advantages

1. **Reuse** (code dobara use hota hai)  
2. **Less redundancy** (duplicate code kam hota hai)  
3. **Maintainability easy hoti hai**  

---

## 🔹 Reuse ka Concept

Inheritance ka main purpose hai:

👉 **Existing class ko use karke new class banana**

### 📌 Steps

1. Pehle ek similar class choose karo  
2. Us se new class inherit karo  
3. Zarurat ke hisaab se new features add ya modify karo  

---

## 🔹 Final Simple Line

👉 **Inheritance = Parent ki properties + apni extra features**
