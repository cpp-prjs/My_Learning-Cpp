* In linux (Ubuntu), g++ is used to compile the C/C++ files.
  E.g. 
  ```
    g++ hello.cpp -o hello.out  // compile the C++ file.
    ./hello.out   // execute the output file.
  ```
* **Demerit of ```cin```**:
  takes 
  i. input as string only.
  ii. contnuous string as input, use alternative - ```getline```.
* **Pointer** - here, any pointer has stored values as address
  E.g. 
  ```
  int a = 5;  // variable stores the value
  int *ptr = nullptr;  // declared and initialised the pointer
  ptr = &a;   // the pointer stores the memory address of the variable.
  ```  
* **Pre-increment & Post-increment** - 
  Pre- operation & then assign the updated value (to the other var)
  Post - assign the original value (to the other var) & then update this var. 
  E.g. 
  ```
  #include<iostream>

  using namespace std;

  int main()
  {
      int a, b = 0;
      int post, pre = 0;
      cout<<"Inital values: \t\t\tpost = "<<post<<" pre= "<<pre<<"\n";
      post = a++;  // post returns 0 (but a=1)
      pre = ++b;   // pre returns 1 (but a=1)
      cout<<"After one postfix and prefix: \tpost = "<<post<<" pre= "<<pre<<"\n";
      post = a++;  // post returns 1 (but a=2)
      pre = ++b;   // pre returns 2 (but a=2)
      cout<<"After two postfix and prefix: \tpost = "<<post<<" pre= "<<pre<<"\n";  
      return 0;
  }
  ```
  
  
  
  
  
  
