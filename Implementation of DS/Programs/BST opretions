#include<bits/stdc++.h>
using namespace std;

class Node{
	public:
	int value;
	Node *left, *right;
};

Node *newNode(int data){
	Node * node = new Node();
	node -> value = data;
	node -> left = node -> right = NULL;
	return node;
}

Node * insert(Node * node, int data){
	if(node == NULL) return newNode(data);
	
	if(node -> value > data){
		node -> left = insert(node -> left, data);
	}else if(node -> value < data){
		node -> right = insert(node -> right, data);
	}
	
	return node;
}

void inorder(Node * node){
	if(node == NULL) return;
	inorder(node -> left);
	cout << node -> value << " ";
	inorder(node -> right);
	
}
Node * mini(Node * node){
	Node * c = node;
	while(c && c->left != NULL){
		c = c -> left;
	} 
	return c;
}

Node * deletion(Node *node, int data){
	if(node == NULL) return node;
	
	if(node -> value > data)
		deletion(node -> left, data);
	else if(node -> value < data)
		deletion(node -> right, data);
	else{
			
		if(node -> left == NULL){
			Node * tmp = node -> left;
			 free(node);
			  return tmp;
		}else if(node -> right == NULL){
			Node * tmp = node -> right;
			 free(node);
			  return tmp;
		}
		Node * tmp = mini(node -> right);
		node -> value = tmp -> value;
		node -> right = deletion(node -> right, tmp->value);
	}
	return node;
}

int main(){
		Node * root = NULL;
		int n;
		cout << "Enter the no of entries to be made:\n";
		cin >> n;
		while(n--){
			cout << "Enter the element:\n";
			int t;
			cin >> t;
			root = insert(root, t);
		}
		inorder(root);
		while(n--)
		{
			
		cout << "Enter the number to be deleted:\n";
		int x;
		cin >> x;
		root = deletion(root, x);
		cout << "Elements after deletion:\n";
		inorder(root);
		cout<<"\n";
	}
}		
		
		
		
		
		
