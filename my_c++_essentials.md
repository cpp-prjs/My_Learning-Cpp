* ### Editor - 
  **Sublime Text 3**.
  
* ### Compilers 
	**Windows** - mingw-w64 <br/>
	**MacOS** - Clang <br/>
	**Linux** - GCC 
	
	#### NOTE: Popular C++ compilers are mingw-w64 for Windows, Clang for XCode for macOS, and GCC on Linux. Make sure your compiler executable is in your platform path so the extension can find it. The extension also supports the Windows Subsystem for Linux.
	
* ### Installation
  In linux (Ubuntu), g++ is used to compile the C/C++ files.
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
  
* ### Demerit of ```cin```:
  takes 
  i. input as string only.
  ii. contnuous string as input, use alternative - ```getline```.
  
* ### Pointer - 
  here, any pointer has stored values as address
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
 
* ### Pre-increment & Post-increment - 
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
  
* ### array - size or length of an array
  ```
  sizeof(userInput)/sizeof(*userInput)  // 160/4 = 40 (defined like - e.g. arr[40])
  ```
  
* ### Function by call or by reference
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
  
* ### OOP (polymorphism, inheritance)
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
  
* ### Templates - 
  [Source](http://www.learncpp.com/cpp-tutorial/131-function-templates/)
  Remember the Stencil analogy. Here, multiple functions with difference of parameter types can be represented with C++ templates.
  E.g. 'max' function
  ```
  // int type
  int max(int x, int y)
  {
      return (x > y) ? x : y;    
  }
  ```
  
  ```
  // double type
  double max(double x, double y)
  {
      return (x > y) ? x : y;    
  }
  ```
  Such functions can be represented with one function with generic type.
  ```
  template <typename T>
  const T& max(const T& x, const T& y)
  {
      return (x > y) ? x : y;
  }
  ```
	
* ### C++ Multilevel Inheritance - 
   ```
	class A
	{ 
	... .. ... 
	};
	class B: public A
	{
	... .. ...
	};
	class C: public B
	{
	... ... ...
	};
   ```

* ### Function by reference vs by value (/pointer) 
```
#include <iostream>

// Function by reference
void swap1(int &a, int &b) {
    int temp = a;
    a = b;
    b = temp;
    std::cout << "changed values a = " << a << " b = " << b <<"\n";
}

// Function by value
void swap2(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
    std::cout << "changed values a = " << *a << " b = " << *b <<"\n";

}

int p = 2;
int q = 3;

int main() {
	swap1(p, q); // pass by reference
	int *x = &p;
	int *y = &q;
	swap2(x, y); // pass by value
	return 0;
}

```

> Say I want to share a web page with you. If I tell you the URL, I'm passing by reference. You can use that URL to see the same web page I can see. If that page is changed, we both see the changes. If you delete the URL, all you're doing is destroying your reference to that page - you're not deleting the actual page itself.

> If I print out the page and give you the printout, I'm passing by value. Your page is a disconnected copy of the original. You won't see any subsequent changes, and any changes that you make (e.g. scribbling on your printout) will not show up on the original page. If you destroy the printout, you have actually destroyed your copy of the object - but the original web page remains intact.
[Read more](https://stackoverflow.com/questions/373419/whats-the-difference-between-passing-by-reference-vs-passing-by-value#)

[SOURCE](https://www.geeksforgeeks.org/passing-by-pointer-vs-passing-by-reference-in-c/)

* ### `auto` keyword - called as "Type Inferring"
	it automatically takes the 'type' of the function, variable.
	
	
	```cpp
	/// This will work
	auto add(int x, int y)
	{
			return x + y;
	}
	
	/// This will NOT work. So, instead use templates.
	void addAndPrint(auto x, auto y)
	{
			std::cout << x + y;
	}
	```
	
	[SOURCE](http://www.learncpp.com/cpp-tutorial/4-8-the-auto-keyword/)

* ### `typedef` - Type definition
	- #### with Variables
	```cpp
	int current_speed ;
	int high_score ;


	void congratulate(int your_score) {
			if (your_score > high_score)
					...
	```
	
	& 
	
	```cpp
	typedef int km_per_hour ;
	typedef int points ;

	km_per_hour current_speed ;  //"km_per_hour" is synonymous with "int" here,
	points high_score ;          //and thus, the compiler treats our new variables as integers.


	void congratulate(points your_score) {
			if (your_score > high_score)
					...
	```
	
	are both identical.
	
	**Inference:** Both sections of code execute identically. However, the use of typedef declarations in the second code block makes it clear that the two variables, while represented by the same data type int, represent different or incompatible data. The definition in congratulate() of your_score indicates to the programmer that current_speed (or any other variable not declared as a points) should not be passed as an argument.
	
	- #### with Structs
	In terms of `struct` typedef is defined as:
	```cpp
	typedef struct {
    int data1;
    char data2;
	} newtype;
	```
	
	- #### with Pointers
	In terms of `pointers`, typedef is defined as;
	```cpp
	typedef int *intptr;   // type name: intptr
                       // new type: int*

	intptr ptr;            // same as: int *ptr
	```
	
	**Inference:** Above, intptr is a new alias with the pointer type int*. The definition, intptr ptr;, defines a variable ptr with the type int*. So, ptr is a pointer which can point to a memory with int type.
	```cpp
	typedef int *intptr;

	intptr cliff, allen;        // both cliff and allen are int* type

	intptr cliff2, *allen2;     // cliff2 is int* type, but allen2 is int** type
															// same as: intptr cliff2;
															//          intptr *allen2;
	```
	
  - #### with structure pointers
	```cpp
	typedef struct Node Node;
	struct Node {
			int data;
			Node *nextptr;
	};
	```
	 
	e.g. 2 -->
	```cpp
	struct Node *startptr, *endptr, *curptr, *prevptr, errptr, *refptr;
	```
	 &
	 
	 ```cpp
	 typedef struct Node* NodePtr;
	 NodePtr startptr, endptr, curptr, prevptr, errptr, refptr;
	 ```
	 are identical.
	 
	- #### with Function pointers
	 TODO - https://en.wikipedia.org/wiki/Typedef#Using_typedef_with_function_pointers
	 
  - #### with Arrays
	 ```cpp
	typedef char arrType[6];    // type name: arrType
														// new type: char[6]

	arrType arr={1,2,3,4,5,6};  // same as: char arr[6]={1,2,3,4,5,6}

	arrType *pArr;              // same as: char (*pArr)[6];
	 ```
	 
  - #### Usage in C++
  ```cpp
  std::vector<std::pair<std::string, int> > values;
  for (std::vector<std::pair<std::string, int> >::const_iterator i = values.begin(); i != values.end(); ++i)
  {
     std::pair<std::string, int> const & t = *i;
     // do something
  }
	 ```
   & 
  ```cpp
  typedef std::pair<std::string, int> value_t;
  typedef std::vector<value_t> values_t;

  values_t values;
  for (values_t::const_iterator i = values.begin(); i != values.end(); ++i)
  {
     value_t const & t = *i;
     // do something
  }
  ```
  are identical.
  
  - #### with templates
  TODO - https://en.wikipedia.org/wiki/Typedef#Use_with_templates

	
* ### Inline functions 
	- CPU stores the memory address of the instruction and then calls the function.
	- copies the arguments of the function on the stack.
	- if the **execution-time** of function < **switching-time** from the caller function to called function (callee).
	- E.g. 
		+ for Small function, the execution time < switching time.
		+ for Large function, the execution time > switching time.
	- C++ provides inline functions to reduce the function call (i.e. switching time).
	- syntax:
	```
	inline return-type function-name(parameters) 
	{
		// Do anything
	}
	```
	- #### NOTE: `inline` is not a command, but a request to the compiler.
	-  Compiler **may** not consider in these circumstances:
		+ If a function contains a loop. (for, while, do-while)
		+ If a function contains static variables.
		+ If a function is recursive.
		+ If a function return type is other than void, and the return statement doesn’t exist in function body.
		+ If a function contains switch or goto statement.
	- Advantages:
		+ Function call overhead doesn’t occur
		+ It also saves the overhead of push/pop variables on the stack when function is called.
		+ It also saves overhead of a return call from a function.
		+ For embedded systems, `inline` functions (if it is small) can yield less code than the function call.
	- Disadvantages:
		+ inlined function consumes additional registers.
		+ too many inline functions leads to large binary executable file size.
		+ too much inlining can reduce your instruction cache hit rate => low speed of instruction fetch from cache memory to primary memory.
		+ For many embedded systems, inline functions may not be useful because code size is more imp. than speed.
	- **Bad** inline programming style
	```
	class S
	{
	public:
		inline int square(int s) // redundant use of inline
		{
			// this function is automatically inline
			// function body
		}
	};
	```
	- **Good** inline programming style
	```cpp
	class S
	{
	public:
		int square(int s); // declare the function
	};
	inline int S::square(int s) // use inline prefix
	{
			// do something
	}
	```
	
	Link - https://www.geeksforgeeks.org/inline-functions-cpp/

* ### `const` methods
	- `const` method function --> not allow them to modify the object on which they are called.
	- E.g.
	```
		#include<iostream>

		using namespace std;

		class Test {

		    int value;

		public:
		    Test(int v = 0) {value = v;}
		    // We get compiler error if we add a line like "value = 100;"
		    // in this function.
		    int getValue() const {return value;}  
		};

		int main() {
		    Test t(20);
		    cout<<t.getValue();
		    return 0;
		}
	```
	- a `const` function can be called on any type of object.
	- But, a non-const function can be called by non-const objects.

	Like 

		```
		#include <iostream>

		using namespace std;

		class Test {
			int value;

			public:
					Test( int v ) {value = v;}

					int getValue() {return value;}
		};

		int main() {
			const Test t(20);
			std::cout << t.getValue() << std::endl;

			return 0;
		}
		```

	gives an error:
		`passing 'const Test' as 'this' argument of 'int 
		Test::getValue()' discards qualifiers`
	
	Link - https://www.geeksforgeeks.org/const-member-functions-c/ 
