

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
