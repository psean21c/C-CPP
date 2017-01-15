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

### pass the 2D array as parameter to a function

```cpp

void printG(int **g,int SIZE){
    for(int i=0;i<SIZE;i++){
    	for(int j=0;j<SIZE;j++){
		cout << g[i][j] << " ";
    	}
    	cout << endl;
    }
	cout << "---------------" << endl;
}

int main(){

        int n = 5;
        int SIZE = n;
        int **graph;
        graph = (int **) malloc(SIZE * sizeof(int*));

        for(int i=0;i<SIZE;i++){
    		graph[i] = (int *) malloc(SIZE * sizeof(int*));
        	for(int j=0;j<SIZE;j++){
        		graph[i][j] = 0;
        	}
        }

        printG(graph, SIZE);
	
	return 0;
}
```
