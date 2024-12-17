# C++ Examination Answers

## SECTION-A (2 marks each)

1. **Define Class**
   - A class is a user-defined data type that encapsulates data and functions that operate on that data
   - It serves as a blueprint for creating objects, combining data representation and methods for manipulating that data

2. **Pointer Operator**
   - The pointer operators are:
     - `*` (dereferencing operator): Used to access the value at the address stored in a pointer
     - `&` (address-of operator): Used to get the address of a variable
   Example:
   ```cpp
   int x = 10;
   int* ptr = &x;    // & gets address of x
   cout << *ptr;     // * gets value at ptr (10)
   ```

3. **Special Characteristics of Friend Function**
   - Can access private and protected members of a class
   - Not a member function of the class
   - Cannot be called using object of the class
   - Can be declared in public or private section of the class
   - Cannot access class members directly

4. **Pure Virtual Function**
   - A virtual function that has no definition in base class
   - Declared by assigning 0:
     ```cpp
     virtual void display() = 0;
     ```
   - Makes the class abstract
   - Must be overridden in derived classes

5. **Polymorphism**
   - Ability of objects to take multiple forms
   - Two types:
     - Compile-time (static): Function overloading, operator overloading
     - Runtime (dynamic): Virtual functions, function overriding

6. **Static Data Member Definition**
   - Defined outside the class using scope resolution operator
   - Only one copy shared by all objects
   Example:
   ```cpp
   class MyClass {
       static int count;
   };
   int MyClass::count = 0;
   ```

7. **Non-overloadable Operators**
   - Scope resolution operator (::)
   - Member selector (.)
   - Member pointer selector (->)
   - Sizeof operator
   - Conditional operator (?:)

8. **Benefits of OOP**
   - Encapsulation of data and behavior
   - Reusability through inheritance
   - Data hiding and abstraction
   - Maintainable and extensible code
   - Modular development

9. **Types of Inheritance**
   - Single inheritance
   - Multiple inheritance
   - Multilevel inheritance
   - Hierarchical inheritance
   - Hybrid inheritance

10. **Token**
    - Smallest individual element of a program
    - Types:
      - Keywords
      - Identifiers
      - Constants
      - Operators
      - Separators

## SECTION-B (5 marks each)

11. **Program to Overload + Operator for Matrices**
```cpp
class Matrix {
    int mat[3][3];
public:
    // Constructor and input methods assumed

    Matrix operator+(Matrix const& obj) {
        Matrix result;
        for(int i = 0; i < 3; i++)
            for(int j = 0; j < 3; j++)
                result.mat[i][j] = mat[i][j] + obj.mat[i][j];
        return result;
    }
};
```

12. **Exception Handling in Class**
```cpp
class DivisionByZero {
private:
    double numerator, denominator;
public:
    class DivideByZeroException {};
    
    double divide() {
        if(denominator == 0)
            throw DivideByZeroException();
        return numerator/denominator;
    }
    
    void setValues(double n, double d) {
        numerator = n;
        denominator = d;
    }
};

// Usage:
try {
    DivisionByZero div;
    div.setValues(10, 0);
    div.divide();
}
catch(DivisionByZero::DivideByZeroException) {
    cout << "Division by zero attempted";
}
```

13. **Virtual Function Explanation**
- Virtual functions enable runtime polymorphism
- Declared using 'virtual' keyword in base class
- Overridden in derived classes
- Late binding through v-table mechanism
Example:
```cpp
class Base {
public:
    virtual void display() {
        cout << "Base class";
    }
};

class Derived : public Base {
public:
    void display() override {
        cout << "Derived class";
    }
};
```

14. **Program to Concatenate Strings**
```cpp
#include <iostream>
#include <string>
using namespace std;

class StringConcat {
    string str;
public:
    StringConcat(string s) : str(s) {}
    
    string concatenate(string s2) {
        return str + s2;
    }
};

int main() {
    StringConcat s1("Hello ");
    cout << s1.concatenate("World");
    return 0;
}
```

15. **Drawbacks of Procedural and Structural Programming**
- Limited code reusability
- Difficulty in managing large programs
- No data hiding mechanism
- Poor data security
- Limited abstraction capabilities
- Difficult maintenance
- No inheritance support
- Limited modularity
- Complex code modification
- Poor real-world modeling

## SECTION-C (10 marks each)

16. **Program to Erase List Elements Using Iterators**
```cpp
#include <iostream>
#include <list>
using namespace std;

class ListManager {
private:
    list<int> numbers;
    
public:
    // Add elements to list
    void addElements(int n) {
        numbers.push_back(n);
    }
    
    // Display list
    void displayList() {
        for(auto it = numbers.begin(); it != numbers.end(); ++it)
            cout << *it << " ";
        cout << endl;
    }
    
    // Erase all elements
    void eraseAll() {
        auto it = numbers.begin();
        while(it != numbers.end()) {
            it = numbers.erase(it);
        }
    }
    
    // Check if list is empty
    bool isEmpty() {
        return numbers.empty();
    }
};

int main() {
    ListManager lm;
    
    // Add elements
    lm.addElements(1);
    lm.addElements(2);
    lm.addElements(3);
    
    cout << "Before erasing: ";
    lm.displayList();
    
    lm.eraseAll();
    
    cout << "After erasing: ";
    lm.displayList();
    
    if(lm.isEmpty())
        cout << "List is empty\n";
        
    return 0;
}
```

17. **Multi-level Inheritance Example**
```cpp
class Animal {
protected:
    string species;
public:
    Animal(string s) : species(s) {}
    virtual void makeSound() {
        cout << "Some sound\n";
    }
};

class Mammal : public Animal {
protected:
    int legs;
public:
    Mammal(string s, int l) : Animal(s), legs(l) {}
    void walk() {
        cout << "Walking on " << legs << " legs\n";
    }
};

class Dog : public Mammal {
private:
    string breed;
public:
    Dog(string s, int l, string b) : Mammal(s, l), breed(b) {}
    
    void makeSound() override {
        cout << "Woof!\n";
    }
    
    void displayInfo() {
        cout << "Species: " << species << endl;
        cout << "Breed: " << breed << endl;
        cout << "Legs: " << legs << endl;
    }
};

// Usage example:
int main() {
    Dog dog("Canis lupus", 4, "German Shepherd");
    dog.displayInfo();
    dog.makeSound();
    dog.walk();
    return 0;
}
```

18. **Control Statements Example**

```cpp
#include <iostream>
using namespace std;

void demonstrateControlStatements(int n) {
    // goto example
    if(n < 0)
        goto negative;
    
    // continue example
    for(int i = 0; i < n; i++) {
        if(i % 2 == 0)
            continue;  // Skip even numbers
        cout << i << " ";
    }
    
    // break example
    for(int i = 0; i < n; i++) {
        if(i > 5)
            break;  // Exit loop if i > 5
        cout << i << " ";
    }
    
    return;  // Return statement
    
negative:
    cout << "Number is negative";
}

int main() {
    // Example usage of goto
start:
    int choice;
    cout << "Enter a number (0 to exit): ";
    cin >> choice;
    
    if(choice != 0) {
        demonstrateControlStatements(choice);
        goto start;
    }
    
    return 0;
}
```

Key points about control statements:

1. **goto**
   - Transfers control to labeled statement
   - Should be used sparingly
   - Useful for breaking nested loops

2. **break**
   - Exits from current loop or switch
   - Useful for terminating loops early
   - Cannot break multiple loops without goto

3. **continue**
   - Skips rest of current iteration
   - Continues with next iteration
   - Useful for skipping specific conditions

4. **return**
   - Exits from current function
   - Returns value to calling function
   - Terminates function execution
