* **Writing Codes** - My personal choice - **Sublime Text 3**.
* In linux (Ubuntu), g++ is used to compile the C/C++ files.
  E.g. 
  ```
    g++ hello.cpp -o hello.out  // compile the C++ file.
  ```
    or
  ```
    g++ -std=c++11 hello.cpp -o hello.out   // compile the C++11 file.
  ```
  ```
    ./hello.out   // execute the output file.
  ```
* **Demerit of ```cin```**:
  takes 
  i. input as string only.
  ii. contnuous string as input, use alternative - ```getline```.
* **Pointer** - here, any pointer has stored values as address
  E.g. 1
  ```
  int a = 5;  // variable stores the value
  int *ptr = nullptr;  // declared and initialised the pointer
  ptr = &a;   // the pointer stores the memory address of the variable.
  ```  
  E.g. 2
  ```
  /*For this program print for each variable
  **print the value of the variable, 
  **then print the address where it is stored. 
  */
  #include<iostream>
  #include<string>

  int main()
  {
      int givenInt = 5;
      float givenFloat = 5.0;
      double givenDouble = 5.6;
      std::string givenString = "abhijit";
      char givenChar = 'a';

      int *pointertogivenInt;
      pointertogivenInt = &givenInt;
      float *pointertogivenFloat;
      pointertogivenFloat = &givenFloat;
      double *pointertogivenDouble ;
      pointertogivenDouble = &givenDouble;
      std::string *pointertogivenString;
      pointertogivenString = &givenString;
      char *pointertogivenChar;
      pointertogivenChar = &givenChar;

      std::cout<<"The pointertogivenInt is "<<pointertogivenInt<<std::endl;
      std::cout<<"The value stored in pointertogivenInt is "<<*pointertogivenInt<<std::endl;

      std::cout<<"The pointertogivenFloat is "<<pointertogivenFloat<<std::endl;
      std::cout<<"The value stored in pointertogivenFloat is "<<*pointertogivenFloat<<std::endl;

      std::cout<<"The pointertogivenDouble is "<<pointertogivenDouble<<std::endl;
      std::cout<<"The value stored in pointertogivenDouble is "<<*pointertogivenDouble<<std::endl;

      std::cout<<"The pointertogivenString is "<<pointertogivenString<<std::endl;
      std::cout<<"The value stored in pointertogivenString is "<<*pointertogivenString<<std::endl;

      std::cout<<"The pointertogivenChar is "<<pointertogivenChar<<std::endl;
      std::cout<<"The value stored in pointertogivenChar is "<<*pointertogivenChar<<std::endl;
      return 0;
  }
  ```
  
  Another example of pointer with  ```this```. Click [here](https://beginnersbook.com/2017/08/cpp-this-pointer/).
 
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
* **array - size or length of an array**
  ```
  sizeof(userInput)/sizeof(*userInput)  // 160/4 = 40 (defined like - e.g. arr[40])
  ```
* **Function by call or by reference**
  ```
  #include<iostream>

  int increment(int input);
  int main()
  {
      int a = 34;
      std::cout<<"Before the function call a = "<<a<<"\n";
      a = increment(a);
      std::cout<<"After the function call a = "<<a<<"\n";
      return 0;
  }
  int increment(int input)
  {
      input++;
      std::cout<<"In the function call a = "<<input<<"\n";
      return input;
  }
  ```
  
  ```
  #include<iostream>

  void increment(int &input); //Note the addition of '&'

  int main()
  {
      int a = 34;
      std::cout<<"Before the function call a = "<<a<<"\n";
      increment(a);
      std::cout<<"After the function call a = "<<a<<"\n";
      return 0;
  }
  void increment(int &input)//Note the addition of '&'
  {
      input++; //**Note the LACK OF THE addition of '&'**
      std::cout<<"In the function call a = "<<input<<"\n";
  }
  ```
* OOP (polymorphism, inheritance)
  E.g.
  ```
  #include <iostream>
  // #include <sstream>


  class Car {   // a class has "data & variables" i.e. "attributes & behavior"
  public:
      int weight;
      std::string color;

      void brake(){   // function to display when called.
          std::cout<<"Brake is applied."<<std::endl;
      }

      int newWeight(){
          weight = 10;
          return weight;
      }

      int newWeight(int wei){  // explains Polymorphism
          weight = wei;
          return weight;
      }
  };

  class Car3: public Car{   // Explains Inheritance

      // No code written. Just calls the "attributes & behavior" of Parent class.
  };


  // Main function
  int main()
  {
      Car3 car1;  // declaration with child class NOT parent class

      car1.brake();
      std::cout<<car1.newWeight()<<std::endl;
      std::cout<<car1.newWeight(40)<<std::endl;

      return 0;
  }
  ```
