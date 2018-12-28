* #### print any type using `template` <br/>
```cpp
using namespace std;

template <typename T>
void print(T a) {
  cout << a << endl;
}

int main() {
  int a = 4;
  int *p = &a;
  int *q = &p;
  print(a); // 4
  print(p); // 0x61fed8
  print(*p); // 4
  print(q); // 0x61fed4
  print(*q); // 0x61fed8
  print(**q); // 4
  
  return 0;
}
```

* #### pointer arithmetic - 2 pointers: p, q;
  - ~~addition~~, ~~multiplication~~, ~~division~~ are NOT allowed. E.g.- p+q, (p * q), p/q;
  - increment, decrement, substraction are allowed. p=p+1, p=p-1, p-q;
  [SOURCE](https://www.youtube.com/watch?v=cKmru3pcggg&t=15m29s)

* #### Prefer using functions by address, NOT by value, especially in case of arrays.
  ```cpp
  void printarray( int *b, int n){
    for(int i = 0; i < n; i++) {
      print(*(b+i));
    }
  }

  int main()
  {
    int a[5] = {1, 3, 5, 6, 7};
    int* p = a;

    printarray(p, 5);

    return 0;
  }
  ```
  [SOURCE](https://www.youtube.com/watch?v=cKmru3pcggg)

* #### `i++` vs `++i` in loops
  ```cpp
  ++i;  // Fetch i, increment it, and return it
  i++;  // Fetch i, copy it, increment i, return copy
  ```
  
  **Recommended**: `++i` always chosen, bcoz it avoids copying any variable. 
  
>> **NOTE: <br/> 
Postfix form of ++,-- operator follows the rule use-then-change , <br/>
Prefix form (++x,--x) follows the rule change-then-use.**
  
  For details, click [here](https://stackoverflow.com/questions/4261708/i-or-i-in-for-loops/4261743#4261743)
  
* #### `const` variable vs `const` pointer
  - `const int x = 8;   // const variable`
  - `const int* y;   // pointer pointing to a const variable`
  - `const int* const z;  // const pointer pointing to a const variable`
  
* #### call by val, ref, pointer
  As per [Google C++ guide](http://drake.mit.edu/styleguide/cppguide.html),
  `In fact, it is a very strong convention in Google code that input arguments are values or const references while output arguments are pointers.`
  
  **Method 1:**
  ```cpp
  void split(const std::string &name, std::string *first, std::string *last)
  {
      std::size_t pos = name.find(" ");
      *first = name.substr(0, pos);
      *last = name.substr(pos + 1);
  }
  std::string name = "Dan Larimer";
  std::string first, last;
  split(name, &first, &last);
  ```
  
  **Method 2:**
  ```cpp
  void split(const std::string &name, std::string& first, std::string& last)
  {
      std::size_t pos = name.find(" ");
      first = name.substr(0, pos);
      last = name.substr(pos + 1);
  }
  std::string name = "Dan Larimer";
  std::string first, last;
  split(name, first, last);
  ```
  
  **Inference**: What you prefer is up to you and comes down to personal style. One reason why the Google C++ Styleguide prefers pointers as output arguments is because it makes it clear at the caller site that the argument is potentially going to be mutated.
  
  [Source](https://cmichel.io/cpp-guide-for-eos-development-call-by-value-reference/)

* #### Differences b/w different function definitions
  Difference b/w 
  1. func( int a, int b, int c)
  2. func( int& a, int& b, int& c)
  3. func( const int& a,const int& b,const int& c)

  Which one is best to use in C++?
  
  **A.**
  Following points to ponder:
  - For primitive types (byte, boolean, int, char, short, long, double, float), reference are rarely useful.
  - For derived types, use `reference`. 
  - And`const` with `reference` is used when the caller (e.g. class) is `const` or `non-const` and the callee is a function (should be defined `const`). Also, considered safe for use in case of derived types i.e. string, class, struct, enum, etc.
  
* In C, the values are passed by value always.
* **POINTERS ARE JUST ADDRESSES**
* #### Print characters of a string
  <details>
    <summary><b>Code:</b></summary>
  <p>

  ```cpp
  #include <iostream>
  #include <string.h>

  int main() {
    char* s;
    std::cout << "Enter a string:" << std::endl;
    std::cin >> s;
    if( s == NULL ) {
      return 1;
    } 
    std::cout << "Output:" << std::endl;
    for( int i = 0; i < strlen(s); ++i ) {
      std::cout << *(s+i) << std::endl;
    }
    return 0;
  }
  ```

  </p>
  <details>
  
> NOTE: string is a array/pointer of characters.
* `malloc()`, `free()` are replaced by `new`, `delete` respectively. 
