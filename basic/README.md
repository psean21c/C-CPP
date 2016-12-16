# Start


### Time

```cpp
#include <time.h>

	time_t t= clock();
  ...
	cout<<(double)(clock()-t)/CLOCKS_PER_SEC<<endl;
```


### vector

```cpp
#include <vector>

    int n 
    vector<int> arr(n);
    for(int i = 0;i < n;i++){
       cin >> arr[i];
    }
```
### Exception format

 * Try-Catch flow

```cpp
#include <cstdio>
#include <iostream>


using namespace std;

int main() {
    string s;
    cin >> s;

    try {
        cout << stoi(s) << endl;
    } catch(...) {
        cout << "Bad String" << endl;
    }

    return 0;
}

```

### map

input
```
3
sam 99912222
tom 11122222
harry 12299933
sam
edward
harry
```

output
```
sam=99912222
Not found
harry=12299933
```

* Requirement

Define map named phoneBook to save the data as below (key,value)


phoneBook = {(sa,m 99912222),(tom, 11122222),(harry, 12299933)}

```cpp

#include <cstdio>
#include <vector>
#include <map>
#include <iostream>

using namespace std;

int main() {
	map<string, int> phoneBook;

	int n;
	cin >> n;

	cin.ignore(256, '\n');
	for (int i = 0; i < n; i++) {
		string name;
		int phone;
		cin >> name;
		cin >> phone;
		phoneBook[name] = phone;
	}

	cin.ignore(256, '\n');
	string name1;
	while (getline(cin, name1)) {
		bool inBook = phoneBook.find(name1) == phoneBook.end();
		if (inBook) {
			cout << "Not found" << endl;
		} else {
			cout << name1 << "=" << phoneBook[name1] << endl;
		}
	}

	return 0;
}


```

