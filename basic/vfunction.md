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


