* print any type using `template` <br/>
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

* pointer arithmetic - 2 pointers: p, q;
  - ~~addition~~, ~~multiplication~~, ~~division~~ are NOT allowed. E.g.- p+q, (p * q), p/q;
  - increment, decrement, substraction are allowed. p=p+1, p=p-1, p-q;
  [SOURCE](https://www.youtube.com/watch?v=cKmru3pcggg&t=15m29s)

* Prefer using functions by address, NOT by value, especially in case of arrays.
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

* `i++` vs `++i` in loops
  ```cpp
  ++i;  // Fetch i, increment it, and return it
  i++;  // Fetch i, copy it, increment i, return copy
  ```
  
  **Recommended**: `++i` always chosen, bcoz it avoids copying any variable. 
  
  For details, click [here](https://stackoverflow.com/questions/4261708/i-or-i-in-for-loops/4261743#4261743)
