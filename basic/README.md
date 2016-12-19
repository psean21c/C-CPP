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
#include <iostream>
#include <algorithm>
#include <vector>

using namespace std;


int main() {
	int n = 0;
	cin >> n;
	vector<int> arr(n);

	for(int i=0;i<n;i++){
		cin >> arr[i];
	}

	sort(arr.begin(),arr.end());
	for(unsigned int i=0;i<arr.size();i++){
		cout << arr[i] << " ";
	}

}
```
TestCase
```
6
4 6 5 3 3 1

>>
1 3 3 4 5 6 
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
### Variable Sized Arrays

https://www.hackerrank.com/challenges/variable-sized-arrays


```c
#include <iostream>
using namespace std;

int main() {

  int n, q;
	cin >> n >> q;
	int** ar = new int*[n];

	for(int i=0;i<n;i++){
		int k;
		cin >> k;
		ar[i] = new int[k];
		for(int j=0;j<k;j++){
			cin >> ar[i][j];
		}
	}


	for(int i=0;i<q;i++){
		int x,y;
		cin >> x >> y;
		cout << ar[x][y] << endl;
	}

	return 0;
}

```


```c

  // 1) Cannot allocate array memory dynamically
	int ar[n][n];
	for(int i=0;i<n;i++){
    ...
		for(int j=0;j<k;j++){
			cin >> ar[i][j];
		}
	}

  // 2) pointer = array
	int** ar = new int*[n];

	for(int i=0;i<n;i++){
		int k;
		cin >> k;
		ar[i] = new int[k];
		for(int j=0;j<k;j++){
			cin >> ar[i][j];
		}
	}



```

---
### Virtual function

https://www.hackerrank.com/challenges/virtual-functions

Excellent question if you want to understand the concept of virtual function and get hands on experience

```c

#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;

/***
Implement two classes - Person + Professor

class Person
class Professor:public Person

***/

int main(){

    int n, val;
    cin>>n; //The number of objects that is going to be created.
    Person *per[n];

    for(int i = 0;i < n;i++){

        cin>>val;
        if(val == 1){
            // If val is 1 current object is of type Professor
            per[i] = new Professor;

        }
        else per[i] = new Student; // Else the current object is of type Student

        per[i]->getdata(); // Get the data from the user.

    }

    for(int i=0;i<n;i++)
        per[i]->putdata(); // Print the required output for each object.

    return 0;

}

```


```c
int student_cnt;
int prof_cnt;

class Person{

public:
	string name;
	int age;
	Person(){}

	Person(string n,int a){
		this->name = n;
		this->age = a;
	}

	virtual void getdata(){
		cout << "Person getdata() :" <<endl;
	}

	virtual void putdata(){
		cout << "Person putdata() :" <<endl;
	}
};

class Professor:public Person{
public:
	int publications;
	int cur_id;

	Professor(){}

	Professor(string n, int a, int p, int c):Person(n,a){
		this->name = n;
		this->age = a;
		this->publications = p;
		this->cur_id = c;
	}
	void getdata(){
		//Walter 56 99
		cin >> name >> age >> publications;
		cur_id=++prof_cnt;

	}

	void putdata(){
		//Walter 56 99 1
		cout << name << " " << age << " " << publications << " " << cur_id << endl;
	}
};

class Student:public Person{
public:
	int marks;
	int cur_id;


	Student(){}
	Student(int c){
		this->cur_id = c;
	}

	virtual void getdata(){
	//Jesse 18 50 48 97 76 34 98
	//Jesse 18 403 1
		cin >> name >> age;
		int sum = 0;
		int a = 0;
		for(int i=0;i<6;i++){
			cin >> a;
			sum += a;
		}
		marks = sum;
		cur_id = ++student_cnt;

	}

	virtual void putdata(){
		cout << name << " " << age << " " << marks << " " << cur_id << endl;

	}
};

```


