
[Original Question](https://www.hackerrank.com/challenges/c-tutorial-stringstream)

input / output
```
23,4,56
========
23
4
56
```

```cpp
#include <sstream>
#include <vector>
#include <cstdio>
#include <iostream>
using namespace std;

int main() {

    string str;
    cin >> str;
	istringstream ss(str);
	string token;

	while(getline(ss, token, ',')) {
	    cout << token << '\n';
	}

    return 0;
}
```


```cpp
#include <sstream>
#include <vector>
#include <iostream>
using namespace std;

vector<int> parseInts(string str) {
    vector<int> result;
    stringstream ss(str);
    int a;
    char ch;
    while(ss >> a){
        result.push_back(a);
        ss >> ch;
    }
    return result;
}

int main() {
    string str;
    cin >> str;
    vector<int> integers = parseInts(str);
    for(int i = 0; i < integers.size(); i++) {
        cout << integers[i] << "\n";
    }
    
    return 0;
}

```
