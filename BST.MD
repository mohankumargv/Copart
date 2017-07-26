class BinarySearchTree {
 
    class Node {
        int key;
        Node left, right;
 
        public Node(int item) {
            key = item;
            left = right = null;
        }
    }
 
    Node root;
 
    BinarySearchTree() { 
    root = null; 
    }
 
    void insert(int key) {
       root = insertRec(root, key);
    }
     

    Node insertRec(Node root, int key) {
 
        /* If the tree is empty, return a new node */
        if (root == null) {
            root = new Node(key);
            return root;
        }
 
        /* Otherwise, recur down the tree */
        if (key < root.key)
            root.left = insertRec(root.left, key);
        else if (key > root.key)
            root.right = insertRec(root.right, key);
 
        /* return the (unchanged) node pointer */
        return root;
    }
 
    // This method mainly calls InorderRec()
    void inorder()  {
       inorderRec(root);
    }
 
    void inorderRec(Node root) 
	{
        if (root != null) 
		{
            inorderRec(root.left);
            System.out.println(root.key);
            inorderRec(root.right);
        }
    }
 

    public static void main(String[] args) 
	{
        BinarySearchTree tree = new BinarySearchTree();
 
        tree.insert(5);
        tree.insert(6);
        tree.insert(4);
        tree.insert(3);
        tree.insert(7);
        tree.insert(2);
        tree.insert(8);
		tree.insert(9);
		tree.insert(1);
		tree.insert(10);
 
        // print inorder traversal of the BST
        tree.inorder();
    }
}

