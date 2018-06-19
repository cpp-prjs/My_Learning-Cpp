* ### Function definition - 
  In **C++**, ```function``` declaration should be before than its use. <br/>
  E.g.
  ```cpp
  void foo(int); // Prototype declaration of foo, seen by main
                 // Must specify return type, name, and argument list types
  int main()
  {
    foo(2); // OK: foo is known, called even though its body is not yet defined
  }
  void foo(int x) //Must match the prototype
  {
    // Define body of foo here
  }
  ```
  
  In **Java**, there is no such rule. Define anywhere.

* ### Pointers & Reference
  In **C++**, define Reference (using the object and putting own label) like this:
  ```cpp
  Box& b;  // defining a reference like Java
  b.setLength(3.5);
  b.setBreadth(5.6);
  b.setHeight(6.7);
  ```
  and Pointer (like a new stack in the memory) like this:
  ```cpp
  Box* b = new Box(args);
  b->setLength(3.5);
  b->setBreadth(5.6);
  b->setHeight(6.7);
  ```
  
  In **Java**, no pointer only refernce.
  ```java
  Box b;
  b.setLength(3.5);
  b.setBreadth(5.6);
  b.setHeight(6.7);
  ```
