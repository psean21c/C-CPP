
# Generic

### C++ Class Templates

[Original Question](https://www.hackerrank.com/challenges/c-class-templates)

input
```
3
string John Doe
int 1 2
float 4.0 1.5
```

output
```
JohnDoe
3
5.5
```

If you take a look at input/output, it is straightfoward to understand the requirement.
You have to return the added value for input regardless of input data types.

```cpp

#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
#include <cassert>
using namespace std;

/*Write the class AddElements here*/
    

int main () {
  int n,i;
  cin >> n;
  for(i=0;i<n;i++) {
    string type;
    cin >> type;
    if(type=="float") {
        double element1,element2;
        cin >> element1 >> element2;
        AddElements<double> myfloat (element1);
        cout << myfloat.add(element2) << endl;
    }
    else if(type == "int") {
        int element1, element2;
        cin >> element1 >> element2;
        AddElements<int> myint (element1);
        cout << myint.add(element2) << endl;
    }
    else if(type == "string") {
        string element1, element2;
        cin >> element1 >> element2;
        AddElements<string> mystring (element1);
        cout << mystring.add(element2) << endl;
    }
  }
  return 0;
}

```

### Answer

```cpp
template<class T>
class AddElements {
	T element;
public:
	AddElements (T arg) {element=arg;}
	T add(T arg) {
		return element + arg;
	}

};

```
---

### Generics

[Original Question](https://www.hackerrank.com/challenges/30-generics)

oupput
```
1
2
3
Hello
World
```
Print element in the different line regardless of input types

```cpp
#include <iostream>
#include <vector>

using namespace std;

// Implement generic function - named printArray


int main() {

    vector<int> vInt{1, 2, 3};
    vector<string> vString{"Hello", "World"};

    printArray<int>(vInt);
    printArray<string>(vString);

    return 0;
}
```

solution
```cpp

// 1)
template<typename T>
void printArray(vector<T> a){
	for(T i:a)cout<<i<<endl;
}

// 2)
template <class T>
void printArray(vector<T> v){
    for(int i=0;i<v.size();i++)
        cout<<v[i]<<endl;
}
```



