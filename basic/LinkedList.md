
#


[LinkedList Basic PDF](http://cslibrary.stanford.edu/103/LinkedListBasics.pdf)

[LinkedList Basic Coding](https://www.codeproject.com/Articles/24684/How-to-create-Linked-list-using-C-C)




### Template for the question

```cpp
#include <iostream>
#include <cstddef>
using namespace std;

class Node {
public:
	int data;
	Node *next;
	Node(int d) {
		data = d;
		next = NULL;
	}
};

class Solution {
public:

	Node* insert(Node *head, int data) {
		//Complete this method
	}

	void display(Node *head) {
		Node *start = head;
		while (start) {
			cout << start->data << " ";
			start = start->next;
		}
	}
};

int main() {
	Node* head = NULL;
	Solution mylist;
	int T, data;
	cin >> T;
	while (T-- > 0) {
		cin >> data;
		head = mylist.insert(head, data);
	}
	mylist.display(head);

}

```
### Requirement

input
```
4
2
3
4
1
```
output
```
2 3 4 1
```

Solution
```cpp

```


---

```cpp
#include <stdio.h>
#include <stdlib.h>


typedef struct linked_list {
	int data;
	struct linked_list *next;
}linked_list;




linked_list* Insert(linked_list *lst,int number){
	struct linked_list *temp;
	printf("=========Insert: %d ============\n",number);


	if(lst == NULL) {
		lst = (linked_list *) malloc(sizeof(linked_list));
		lst->data = number;
		lst->next = NULL;
	} else {
		temp = lst;
		while(temp->next != NULL) {
		temp = temp->next;
		}
		temp->next = (linked_list *) malloc(sizeof(linked_list));
		if(temp->next == NULL){
			printf("Error! memory is not available\n");
			exit(0);
		}
		temp = temp->next;
		temp->data = number;
		temp->next = NULL;
	}


	return lst;


}


void Print(linked_list *lst){
	linked_list *temp_list;
	temp_list = lst;    


	do{
		printf("%d ", temp_list->data);
		temp_list = temp_list->next;
	}while(temp_list != NULL) ;


	printf("\n");
}




linked_list* Reverse(linked_list *lst){
	linked_list *reverse = NULL;
	linked_list *temp;


	while(lst != NULL){
		temp = lst->next;
		lst->next = reverse;
		reverse = lst;
		lst =temp;
	}
	return reverse;
}


void Delete(linked_list *lst,int num){
	linked_list *temp;
	linked_list *del;
	temp = (linked_list *) malloc(sizeof(linked_list));
	del = (linked_list *) malloc(sizeof(linked_list));
	del = lst;
	printf("=========Delete: ============\n");
	if(lst->data == num){
		temp = lst->next;
		free(lst);
		lst = temp;
	}else{
		do{
			printf("delete>>1 %d \n", lst->data);
			if(lst->data == num){
				printf("found %d \n",lst->data);
			}
			//printf("delete>>2 %d \n", lst->data);
			temp = lst;
			lst = lst->next;
		}while(lst != NULL) ;
	}


	printf("\n");
}


void main(){
	printf("Linked List Program\n");
	linked_list *start_node = NULL;


	start_node = Insert(start_node,10);
	Print(start_node);


	start_node = Insert(start_node,20);
	Print(start_node);


	start_node = Insert(start_node,30);
	Print(start_node);


	start_node = Insert(start_node,40);
	Print(start_node);


	start_node = Reverse(start_node);
	Print(start_node);

}

```

