
[Original question](https://www.hackerrank.com/challenges/box-it)

Need to understand the data type: 

`long long` It's an integer, at least as big as long.

```cpp

#include<bits/stdc++.h>

using namespace std;
/***
class Box{

};

Implement the class Box
l,b,h are integers representing the dimensions of the box

The class should have the following functions :

Constructors:
Box();
Box(int,int,int);
Box(Box);


int getLength(); // Return box's length
int getBreadth (); // Return box's breadth
int getHeight ();  //Return box's height
long long CalculateVolume(); // Return the volume of the box

Overload operator < as specified
bool operator<(Box& b)

Overload operator << as specified
ostream& operator<<(ostream& out, Box& B)

***/


void check()
{
	int n;
	cin>>n;
	Box temp;
	for(int i=0;i<n;i++)
	{
		int type;
		cin>>type;
		if(type ==1)
		{
			cout<<temp<<endl;
		}
		if(type == 2)
		{
			int l,b,h;
			cin>>l>>b>>h;
			Box NewBox(l,b,h);
			temp=NewBox;
			cout<<temp<<endl;
		}
		if(type==3)
		{
			int l,b,h;
			cin>>l>>b>>h;
			Box NewBox(l,b,h);
			if(NewBox<temp)
			{
				cout<<"Lesser\n";
			}
			else
			{
				cout<<"Greater\n";
			}
		}
		if(type==4)
		{
			cout<<temp.CalculateVolume()<<endl;
		}
		if(type==5)
		{
			Box NewBox(temp);
			cout<<NewBox<<endl;
		}

	}
}

int main()
{
	check();
}

```

TestCase-1

input
```
11
1
2 3 84 2
4
2 2 39 21
5
4
3 4 56 5
2 43 45 39
3 43 48 89
3 43 45 40
3 43 31 28
```
output
```
0 0 0
3 84 2
504
2 39 21
2 39 21
1638
Greater
43 45 39
Greater
Greater
Lesser
```

Testcase-2

input
```
5
2 3 4 5
4
5
4
2 4 6 7
```

output
```
3 4 5
60
3 4 5
60
4 6 7
```


Below is the one of solutions

```cpp
class Box{
private:
	int l,b,h;
public:
	 Box(){l = 0; b = 0; h = 0;}
	 Box(const Box& B){ l = B.l; b = B.b; h = B.h;}
	 Box(int l,int b,int h){
		 this->l = l;
		 this->b = b;
		 this->h = h;
	 }

	 int getLength(){
		 return l;
	 }
	 int getBreadth(){
		 return b;
	 }
	 int getHeight (){
		 return h;
	 }
	 long long CalculateVolume(){
		 long long volume = (long long)l*(long long)b*(long long)h;
		 return volume;
	 }

	 bool operator<(Box& B){
		    if ((l < B.l) or (b < B.b && l == B.l) or (h < B.h && l == B.l && b == B.b))
		        return true;
		    else
		        return false;
	 }

	 friend ostream& operator << (ostream& out, Box& B){
		 return out << B.l << " " << B.b << " " << B.h;
	 }
};

```

