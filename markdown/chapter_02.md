# 01. Information Hiding

## Definition
- **"Showing only those details to the outside world which are necessary, and hiding all other details."**
- Objects ke attributes aur behaviors dusri classes se hidden hotay hain  
- Har object ki sari information usi object ke andar store hoti hai  
- Yeh information outside world se hidden hoti hai  
- Isay sirf object khud hi manipulate kar sakta hai  

---

# 02.1 Information Hiding

Information Hiding OOP ka ek bohat important principle hai jo real life se inspired hai.  
Iska matlab hai ke har information har kisi ke liye accessible nahi honi chahiye.  
Private information sirf uske owner tak hi limited honi chahiye.  

---

## Information Hiding ka Matlab

**“Sirf wohi details bahar ki duniya ko dikhana jo zaroori hoon, aur baqi sab details chhupa lena.”**

---

## Real Life Examples of Information Hiding

### 1. Ali ka Example
- Ali ka naam aur personal information uske brain mein hoti hai  
- Hum usay directly access nahi kar sakte  
- Agar humein information chahiye ho to humein Ali se poochna padega  
👉 Aur yeh Ali par depend karta hai ke wo kitni information share kare  

---

### 2. Email Server ka Example
- Email server ke paas millions users ka data hota hai  
- Jab hum request karte hain to sirf hamara apna data milta hai  
- Kisi aur ka data maangne par request reject ho jati hai  

---

### 3. Phone SIM ka Example
- SIM card mein kai phone numbers save ho sakte hain  
- Hum directly SIM se numbers read nahi kar sakte  
- Phone-set yeh kaam karta hai  
👉 Agar owner ne permission na di ho to numbers access nahi hotay  

---

## OOP mein Information Hiding

Object Oriented Programming mein objects hote hain jinke apne:

- **Attributes (data)**
- **Behaviors (functions)**  

👉 Yeh dono dusri classes se hidden hotay hain  

Is liye hum kehte hain ke OOP, Information Hiding ka principle follow karta hai.  

---

## OOP Perspective se Definition

**“Object ki details (state aur behavior) ko users se chhupa dena Information Hiding kehlata hai.”**

---

## Users se Murad

- Kisi doosri class ka object jo is class ke functions ko call karta hai  
- Ya koi aur program jo is class ko use karta hai  

---

## Information Hiding Kaise Achieve Hoti Hai?

OOP mein Information Hiding in points ke through achieve hoti hai:

- Har object ki sari information us object ke andar store hoti hai  
- Yeh information outside world se hidden hoti hai  
- Isay sirf woh object khud hi manipulate (change/use) kar sakta hai  

---

## Advantages of Information Hiding

### 1. Simplicity
- Implementation details hidden hoti hain  
- Sirf objects aur unki interaction nazar aati hai  
👉 System samajhna easy ho jata hai  

---

### 2. Change Control
- Function ki implementation sirf class ke andar hoti hai  
- Agar andar changes karein to bahar system affect nahi hota  

---

## Conclusion

Hum Information Hiding achieve karte hain:

- **Encapsulation ke through**
- **Abstraction ke through**


# 02.2 Encapsulation

## Definition
Encapsulation ka matlab hai:  
**“Hum kisi object ki tamam characteristics ko usi object ke andar band (enclose) kar dete hain.”**

**we have enclosed all the characteristics of an object in the object 
itself**

Encapsulation aur Information Hiding aapas mein bohat closely related concepts hain.  
👉 Information hiding, encapsulation ke through achieve hoti hai.

---

## Encapsulation ki Explanation

Jaise hum ne pehle padha tha, object ki characteristics mein shamil hota hai:

- **Data members (data)**
- **Behavior (functions)**

Is liye hum kehte hain:  
👉 Data aur behavior dono ek object ke andar tightly connected hote hain.

Aur:

- Object ki internal information (structure)
- Aur uski implementation details

👉 Dono bahar ki duniya se hidden hoti hain.

---

## Examples of Encapsulation

### Ali ka Example

Pichle lecture ka example lete hain:

- Ali apni personal information apne andar store karta hai  
- Uska behavior bhi usi ke andar hota hai  

Ab:  
👉 Yeh Ali par depend karta hai ke wo apni information share kare ya nahi  

Agar koi dusra object real life mein Ali ka behavior (jaise walking) use karna chahe:  
👉 Wo bina Ali ki permission ke use nahi kar sakta  

Is liye hum kehte hain:  
👉 Ali ke attributes aur behavior uske andar encapsulated hain  

---

### Interface ka Concept

Koi bhi dusra object Ali ke baare mein kuch nahi janta jab tak:  
👉 Ali khud interface ke through information share na kare  

---
---

### Phone ka Example

Phone ke andar bhi:

- Data hota hai  
- Behavior hota hai (data show karna)  

Hum sirf tabhi phone ka data access kar sakte hain:  
👉 Jab phone ka interface allow kare  

---

## Advantages of Encapsulation

### a. Simplicity aur Clarity

- Saara data aur functions objects ke andar hotay hain  
- Program mein koi bhi cheez random nahi hoti  

👉 Is se har object ka purpose samajhna easy ho jata hai  

---

### b. Low Complexity

- Data aur functions hidden hotay hain  
- Har object ka apna specific behavior hota hai  

👉 Code simple rehta hai aur unnecessary dependencies nahi hoti  

---

### c. Better Understanding

- Har object ka apna role aur relation hota hai  

👉 Sirf object diagrams dekh kar poora system easily samajh aa jata hai  

---

# 📘 Encapsulation (OOP in C++)

## 🔹 Definition
Encapsulation ka matlab hai **data (variables) aur functions (methods) ko ek class ke andar wrap karna** aur **direct access ko restrict karna**.

👉 Simple: *Data ko protect karna*

---

## 🔹 Key Points
- Data ko `private` banaya jata hai  
- Access ke liye `public` methods (getter/setter) use hote hain  
- Unauthorized access ko roka jata hai  

---

## 🔹 Real Life Example
**ATM Machine 💳**

- User sirf:
  - PIN enter karta hai  
  - Amount select karta hai  

- System ka internal data hidden hota hai  

👉 Yeh **Encapsulation** hai (data protected hai)

---

## 🔹 C++ Example

```cpp
#include <iostream>
using namespace std;

class BankAccount {
private:
    int balance; // hidden data

public:
    void setBalance(int b) {
        balance = b;
    }

    int getBalance() {
        return balance;
    }
};

int main() {
    BankAccount obj;
    
    obj.setBalance(5000);  // setting value
    cout << obj.getBalance();  // getting value

    return 0;
}

```

---
---
# 📘 Abstraction (OOP in C++)

## 🔹 Definition
Abstraction ka matlab hai **sirf important cheezon ko dikhana aur unnecessary details ko hide karna**.

👉 Simple: *Complex cheez ko simple banana*

---

## 🔹 Key Points
- User ko sirf required information dikhai jati hai  
- Internal implementation hidden hoti hai  
- Interface simple aur easy hota hai  
- Complexity reduce hoti hai  

---

## 🔹 Real Life Example
**Car 🚗**

- Driver sirf:
  - Steering  
  - Brake  
  - Accelerator use karta hai  

- Engine ka internal system hidden hota hai  

👉 Yeh **Abstraction** hai  

---

## 🔹 C++ Example

```cpp
#include <iostream>
using namespace std;

class Car {
public:
    void start() {
        cout << "Car started" << endl;
    }
};

int main() {
    Car c;
    c.start(); // simple interface use

    return 0;
}

``` 


# 📘 02.3 Interface (OOP)

## 🔹 Interface ki Definition

Interface ek aisi set of functions hoti hai jo ek object dusray objects ko expose (show) karna chahta hai.

Jaisa ke hum pehle discuss kar chukay hain ke har object ka data aur behavior usi object ke andar hidden hota hai.  
Is liye hum interface ka concept use karte hain taake object apna behavior outer world objects ko show kar sake.

---

## 🔹 Key Points

- Different objects ko kisi object ke different functions ki zaroorat hoti hai  
- Is liye ek object ka interface different objects ke liye different ho sakta hai  
- Interfaces object communication ke liye zaroori hoti hain  
- Har object apna interface (operations) dusray objects ko provide karta hai  
- In interfaces ke through objects ek dusray se communicate karte hain  

---

## 🔹 Example – Car ka Interface 🚗

- Steering wheel chalana  
- Speed barhana (Accelerate)  
- Gear change karna  
- Brakes lagana  
- Lights on/off karna  

---

## 🔹 Example – Phone ka Interface 📱

- Number input karna  
- Call karna  
- Call disconnect karna  
- Number ko address book mein add karna  
- Number remove karna  
- Number update karna  


# 📘 02.4 Implementation (OOP)

## 🔹 Definition
Implementation ka matlab hota hai ke kisi object ke behavior ko actual mein OOP language (jaise C++) mein likhna aur banana.

---

## 🔹 Implementation ke 2 Main Parts

### 1. Internal Data Structure
- Yeh object ki state ko store karta hai (data members ki values)  
- Yeh hidden hota hai (direct access nahi hota)  

### 2. Functionality (Member Functions)
- Yeh functions hotay hain jo object ka behavior define karte hain  

---

## 🔹 Examples of Implementation

### a. Gear Box (Car System)

- Gear box ek object hai jiska apna structure aur kaam hota hai  

Implementation mein:

- Gear box ka **physical structure**  
- Gear change karne ka **function (mechanism)**  

✔ Yani:
- Data Structure → Gear box ka mechanical structure  
- Functionality → Gear change system  

---

### b. Address Book (Phone)

- Phone ke SIM mein contacts save hotay hain  

✔ Mapping:
- SIM card ka structure → Data Structure  
- Phone ke read/write operations → Functionality  

---

# 📘 02.5 Separation of Interface & Implementation

## 🔹 Definition
Is concept mein hum sirf object ka **interface (functions)** bahar dikhate hain  
aur **implementation (andar ka kaam)** hide kar dete hain  

---

## 🔹 Benefit
- Interface independent ho jata hai implementation se  
- Andar ka system change ho sakta hai bina interface change kiye  

---

## 🔹 Achieved By
- Encapsulation  
- Information Hiding  

---

## 🔹 Real Life Example (Car 🚗)

Driver ke paas ek standard interface hota hai:

- Steering  
- Brake  
- Accelerator  

Driver ko farq nahi padta:

- Car ka model kya hai  
- Engine kis type ka hai  
- Fuel kya use ho raha hai  

👉 Same interface se har car chala leta hai  

---

# 📘 02.6 Messages

## 🔹 Definition
Objects ek dusre se **messages ke zariye communicate karte hain**  

👉 Message ka matlab hota hai:
**Ek object ka dusre object ka function call karna**

---

## 🔹 Examples

- Person car ko **"stop"** ka message deta hai → brakes laga kar  
- Person phone ko **"call karo"** ka message deta hai → button press karke  

---

# 📘 02.7 Summary

- Information hiding, encapsulation ke through hoti hai  
- Encapsulation aur information hiding ek dusre se related hain  
- Interface hume available functions ki list deta hai  
- Ek object ke multiple interfaces ho sakte hain  
- Interface aur implementation alag rakhe jate hain  
- Objects ek dusre se messages ke zariye communicate karte hain  
