# Start


### 1) Timestamp

```cpp
#include <time.h>

	// 1)
	time_t t= clock();
  ...
	cout<<(double)(clock()-t)/CLOCKS_PER_SEC<<endl;
	
	// 2)
	clock_t start = clock();
...
	fprintf(stderr, "elapsed time #5 : %f\n", double(clock() - start) / CLOCKS_PER_SEC); start = clock();
	
```


### 2) Vector

* Declaration:

`vector<int>v;` (creates an empty vector of integers)

* Size:

`int size=v.size();`

* Pushing an integer into a vector:

`v.push_back(x);`(where x is an integer.The size increases by 1 after this.)

* Popping the last element from the vector:

`v.pop_back(); `(After this the size decreases by 1)

* Sorting a vector:

`sort(v.begin(),v.end());` (Will sort all the elements in the vector)

Use basic vector operators, read input and save it to vector and sort them.
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

 * Vector initialzed
```cpp
	vector<vector<int>> array2D;
	array2D.resize(n);
	for (int i = 0; i < n; ++i){
		array2D[i].resize(n);
	}
```	

### 3) Define

```cpp
#define FOR(i,n) for(int i = 0; i < (n); ++i)
#define FOR1(i,n) for(int i = 1; i < (n); ++i)

```

### 4) Exception format

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

### 5) Map

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

### 6) Queue

```cpp
// My Solution
	void levelOrder(Node * root){
		if(root == NULL) return;

		queue<Node *> q;
		q.push(root);

		while(!q.empty()){
			Node* tree = q.front();
			q.pop();

			cout << tree->data << " ";
			if(tree->left) q.push(tree->left);
			if(tree->right) q.push(tree->right);
		}

	}
// Others

     void levelOrder(Node* root){
  	
       queue <Node*> q;
       q.push(root);
        // Don't use recursion on bfs
          
        while (!q.empty())
        {
            Node* current = q.front();
            q.pop();
            cout << current->data << " ";
            
            if (current->left != NULL)
                q.push(current->left);
            
            if (current->right != NULL)
                q.push(current->right);
        }
	
    }
```
