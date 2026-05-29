# Object Oriented Programming – Chapter 06 Detailed Notes (Roman Urdu)

# 06.1 Class Compatibility

## Definition
Aik class dusri class ke sath **behaviorally compatible** tab hoti hai jab woh dusri class ke tamam operations ko support kare.

Aisi class ko **Subtype** kaha jata hai.

Matlab:

> Agar derived class base class ke tamam kaam kar sakti hai to derived class, base class ka subtype hoti hai.

---

## Important Point
Derived class ko base class ki jagah use kiya ja sakta hai.

Iska reason:
- Derived class base class ki properties aur operations inherit karti hai.
- Is liye derived class base class ke tamam legal messages handle kar leti hai.

---

## Real Life Example

### Example 1: Vehicle

```text
Vehicle
 ├── Car
 ├── Bike
 └── Bus
```

Agar Vehicle class mein operation ho:

```text
start()
```

To Car, Bike aur Bus sab `start()` operation perform kar sakte hain.

Is liye:
- Car is subtype of Vehicle
- Bike is subtype of Vehicle
- Bus is subtype of Vehicle

---

# 06.2 Polymorphism

## Definition
Polymorphism ka matlab hai:

> “Same message but different behavior”

Ya:

> Aik hi operation different objects par different tareeqe se kaam kare.

---

## General Meaning
Real world mein bhi aik cheez ki multiple forms hoti hain.

### Example
- Diamond
- Coal

Dono Carbon ki forms hain.

---

# 06.3 Polymorphism in OO Model

OO model mein different objects aik hi message ka different response dete hain.

Sender ko receiver ki exact class jaanne ki zarurat nahi hoti.

Sender sirf message send karta hai.
Receiver apne hisaab se correct method execute karta hai.

---

## Simple Programming Example

```javascript
cat.speak()
dog.speak()
cow.speak()
```

### Output

```text
Cat  -> Meow
Dog  -> Bark
Cow  -> Moo
```

Yahan:
- Message same hai = `speak()`
- Behavior different hai

Isi ko polymorphism kehte hain.

---

## Real Life Example

### Remote Control Example

Aik remote ka button same hota hai:

```text
Power ON
```

Lekin:
- TV ON ho jata hai
- AC ON ho jata hai
- Fan ON ho jata hai

Button same hai lekin behavior alag hai.

Yeh polymorphism hai.

---

## Sender aur Receiver

### Sender
Jo message bhejta hai.

### Receiver
Jo message receive karta hai.

---

## Example

```javascript
shape.draw()
```

Yahan:
- `draw()` message hai
- Shape receiver hai

Agar object Circle hua to circle draw hoga.
Agar object Triangle hua to triangle draw hoga.

---

# Graphic Editor Example

## Problem Statement
Aik graphic editor banana hai jo:

- Line draw kare
- Circle draw kare
- Triangle draw kare

User:
- Shape select kar sake
- Shape move kar sake
- Shape rotate kar sake

Shapes ko group bhi kiya ja sake.

Group aik single shape ki tarah behave kare.

---

# Step 1 – Identify Classes

## Classes kya hoti hain?
Classes objects ka blueprint hoti hain.

Problem statement mein nouns dhoonde jate hain.

---

## Extracted Nouns

- Editor
- User
- Shape
- Line
- Circle
- Triangle
- Group
- Menu
- View

---

# Step 2 – Remove Irrelevant Classes

## Editor
Editor poore system ka naam hai.
Is liye is ka object nahi banega.

---

## User
User system ke bahar hai.
Yeh external actor hai.

---

# Final Classes

- Shape
- Line
- Circle
- Triangle
- Group
- Menu
- View

---

# Step 3 – Identify Associations

## Association
Objects ke darmiyan relationship ko association kehte hain.

---

## Example

### Group Relationship

Statement:

```text
Individual shapes can be grouped together
```

Is se pata chala:

- Group contains Line
- Group contains Circle
- Group contains Triangle

---

# Composition Relationship

Agar aik object dusre objects par strongly depend kare to usay composition kehte hain.

### Example

Group ke andar:
- Shapes
- Other groups

ho sakte hain.

---

# Aggregation Relationship

### View Relationship

View:
- Lines show karta hai
- Circles show karta hai
- Triangles show karta hai
- Groups show karta hai

Is liye:

```text
View HAS-A Shapes
```

Yeh aggregation hai.

---

# Simple Association

### Menu aur View

Menu View ko message bhejta hai.

```text
Menu ---> View
```

Yeh One-Way Simple Association hai.

---

# Step 4 – Identify Attributes

## Attributes kya hote hain?
Object ki properties ko attributes kehte hain.

---

# Shape Attributes

## Line
- Color
- Vertices
- Length

---

## Circle
- Color
- Vertices
- Radius

---

## Triangle
- Color
- Vertices
- Angle

---

## Shape
- Color
- Vertices

---

## Group
- noOfObjects

---

## View
- noOfObjects
- selected

---

## Menu
- name
- isOpen

---

# Step 5 – Identify Operations

## Operations kya hoti hain?
Objects ke actions ko operations kehte hain.

---

# Common Operations

## Shape
- Draw
- Select
- Move
- Rotate

---

## Line
- Draw
- Select
- Move
- Rotate

---

## Circle
- Draw
- Select
- Move
- Rotate

---

## Triangle
- Draw
- Select
- Move
- Rotate

---

## Group
- Draw
- Select
- Move
- Rotate

---

## Menu
- Open
- Select
- Move
- Rotate

---

## View Operations

- Add
- Remove
- Group
- Show
- Select
- Move
- Rotate

---

# Real Life Example of Operations

## Car Example

### Attributes
- color
- model
- speed

### Operations
- start()
- stop()
- accelerate()
- brake()

---

# Step 6 – Identify Inheritance

## Inheritance kya hoti hai?

Jab aik class dusri class ki properties aur operations inherit kare.

---

# Keywords

Inheritance identify karne ke liye:

- such as
- for example
- is a kind of

jaise words dhoonde jate hain.

---

# Example

```text
Shapes such as Line, Circle and Triangle
```

Matlab:

- Line is a Shape
- Circle is a Shape
- Triangle is a Shape

---

# Inheritance Hierarchy

```text
Shape
 ├── Line
 ├── Circle
 ├── Triangle
 └── Group
```

---

# Group Inherits from Shape

Statement:

```text
Group behaves like a single shape
```

Is liye:

```text
Group IS-A Shape
```

---

# Refining the Object Model

Inheritance apply karne ke baad model ko improve kiya jata hai.

---

# Shared Associations

## View
View har tarah ki shape contain karta hai.

## Group
Group har tarah ki shape contain karta hai.

---

# Shared Attributes

Shape ki attributes:

- color
- vertices

Automatically inherit hongi:
- Line
- Circle
- Triangle
- Group

---

# Shared Operations

Shape ki operations:

- select()
- move()
- rotate()

Automatically inherit hongi.

---

# Overriding

## Draw Operation
Sab classes mein draw operation hai.

Lekin:
- Circle alag tareeqe se draw hota hai
- Triangle alag tareeqe se draw hota hai
- Line alag tareeqe se draw hoti hai

Is liye draw method override hota hai.

---

# Real Life Example of Overriding

## Animal Example

```javascript
class Animal {
   sound()
}

class Cat extends Animal {
   sound() => Meow
}

class Dog extends Animal {
   sound() => Bark
}
```

Yahan:
- Method same hai = `sound()`
- Behavior different hai

Yeh overriding + polymorphism hai.

---

# Important Definitions

## Class
Objects ka blueprint.

## Object
Class ka instance.

## Attribute
Object ki property.

## Operation
Object ka action/function.

## Association
Objects ke darmiyan relationship.

## Aggregation
Weak HAS-A relationship.

## Composition
Strong HAS-A relationship.

## Inheritance
IS-A relationship.

## Polymorphism
Same message, different behavior.

## Overriding
Child class ka parent method ko apne tareeqe se implement karna.

---

# Short Summary

## Class Compatibility
Derived class base class ki jagah use ho sakti hai.

## Polymorphism
Same function different objects par different result deta hai.

## Association
Objects ke darmiyan relation.

## Attributes
Object ki properties.

## Operations
Object ke actions.

## Inheritance
Child class parent class ki cheezein inherit karti hai.

## Overriding
Child class apna own implementation deti hai.

