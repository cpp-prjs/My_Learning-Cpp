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

* pointer arithmetic
  - ~~addition~~, ~~multiplication~~, ~~division~~ are NOT allowed.
  - increment, decrement, substraction are allowed.

* Prefer using functions by address, NOT by value, especially in case of arrays.
  [SOURCE](https://www.youtube.com/watch?v=cKmru3pcggg)
