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
