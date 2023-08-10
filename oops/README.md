# OBJECT ORIENTED PROGRAMMING

#### Summary of OOPs

<details>
<summary>Answer</summary>
<p>
1. Object - Instance of Class
2. Class - Blue print of Object
3. Encapsulation - Protecting our Data
4. Polymorphism - Different behaviors at different instances
5. Abstraction - Hiding our irrelevant Data
6. Inheritence - One property of object is acquiring to another property of object
</p>
</details>

---

#### OOPs advantages

<details>
<summary>Answer</summary>
<p>

- Modularity (Easy troubleshooting, Debugging)
- Flexibility (Polymorphism)
- Reusability (Inheritance)
- Security (Abstraction)
- Design Benefits (Fewer flaws, Eliminating risks, Fixing bugs)

</p>
</details>

---

#### Explain Polymorphism and Types of Polymorphism

<details>
<summary>Answer</summary>
<p>

- **Compile Time Polymorphism (early binding)**

  - Method overloading

  ```java
    void gfg() { ... }
    void gfg(int num1 ) { ... }
    void gfg(float num1) { ... }
    void gfg(int num1 , float num2 ) { ... }
  ```

  - Operator overloading

  ```java

  public class GFG {
    // function for adding two integers
    void add(int a, int b) {
      int sum = a + b;
      System.out.println(" Addition of two integer :"+ sum);
    }

    // function for concatenating two strings
    void add(String s1, String s2) {
      String con_str = s1 + s2;
      System.out.println("Concatenated strings :"+ con_str);
    }

    public static void main(String args[]) {
      GFG obj = new GFG();
      // addition of two numbers
      obj.add(10, 10);
      // concatenation of two string
      obj.add("Operator ", " overloading ");
    }
  }
  ```

- **Runtime Polymorphism (late binding)**

  - Method overriding

  ```java
  class Bike {
    void run(){System.out.println("running");}
  }

  class Splendor extends Bike {
    void run() {
      System.out.println("running safely with 60km");
    }

    public static void main(String args[]) {
      Bike b = new Splendor(); //upcasting
      b.run();
    }
  }
  ```

</p>
</details>

---

#### What is Encapsulation?

<details>
<summary>Answer</summary>
<p>

Encapsulation in Java is a process of wrapping code and data together into a single unit, for example, a capsule which is mixed with several medicines

```java

//A Java class which is a fully encapsulated class.
//It has a private data member and getter and setter methods.
package com.javatpoint;
  public class Student {
  //private data member
  private String name;
  //getter method for name
  public String getName() {
    return name;
  }
  //setter method for name
  public void setName(String name) {
    this.name=name
  }
}

```

</p>
</details>

---

#### What is Abstraction?

<details>
<summary>Answer</summary>
<p>

Abstraction is a process of hiding the implementation details and showing only functionality to the user. Another way, it shows only essential things to the user and hides the internal details, for example, sending SMS where you type the text and send the message. You don't know the internal processing about the message delivery.

```java

abstract class Bike {
  abstract void run();
}

class Honda4 extends Bike {
  void run() {
    System.out.println("running safely");
  }

  public static void main(String args[]) {
    Bike obj = new Honda4();
    obj.run();
  }
}
```

</p>
</details>

---

####

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

####

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

####

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

####

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---

####

<details>
<summary>Answer</summary>
<p>

</p>
</details>

---
