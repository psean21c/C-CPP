
```cpp
#include <iostream>
#include <bitset> 

using namespace std;

int main()
{
   bitset<4> mybits;
   cout << mybits << "\t\t" << mybits.to_ulong() << endl;
   mybits.set();
   cout << mybits << "\t\t" << mybits.to_ulong() << endl;
   
   int n = 16;
   string str = bitset<32>(n).to_string();
   cout << str << endl;

   cout << __builtin_ctz(n) << endl;
   cout << __builtin_clz(n) << endl;
   cout << __builtin_popcount(n) << endl;
   
   
   return 0;
}

```

```
0000            0
1111            15
00000000 00000000 00000000 00010000 
4
27
```
