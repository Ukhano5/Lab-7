# Lab-7
Muhammad Umair
12370
SE 3rd C
# Q1: Create a Node class to represent individual nodes in a tree.
class Node:
    def __init__(self, key):
        self.key = key
        self.left = None
        self.right = None

# Output for Q1: No direct output, as it is a class definition.

# Q2: Implement a function to insert a node into a binary tree.
def insert_node(root, key):
    if root is None:
        return Node(key)
    if key < root.key:
        root.left = insert_node(root.left, key)
    else:
        root.right = insert_node(root.right, key)
    return root

# Output for Q2: No direct output, as it is a function definition.

# Q3: Write functions to perform preorder, inorder, and postorder traversals of a binary tree.
def preorder_traversal(root):
    if root:
        print(root.key, end=" ")
        preorder_traversal(root.left)
        preorder_traversal(root.right)

def inorder_traversal(root):
    if root:
        inorder_traversal(root.left)
        print(root.key, end=" ")
        inorder_traversal(root.right)

def postorder_traversal(root):
    if root:
        postorder_traversal(root.left)
        postorder_traversal(root.right)
        print(root.key, end=" ")

# Output for Q3:
# Preorder Traversal: 10 5 3 7 15 12 18
# Inorder Traversal: 3 5 7 10 12 15 18
# Postorder Traversal: 3 7 5 12 18 15 10

# Q4: Write a function to calculate the height of a binary tree.
def calculate_height(root):
    if root is None:
        return 0
    left_height = calculate_height(root.left)
    right_height = calculate_height(root.right)
    return max(left_height, right_height) + 1

# Output for Q4: Height of the Binary Tree: 3

# Q5: Implement a function to count the number of nodes in a binary tree.
def count_nodes(root):
    if root is None:
        return 0
    return 1 + count_nodes(root.left) + count_nodes(root.right)

# Output for Q5: Number of Nodes in the Binary Tree: 7

# Q6: Write a function to determine if a binary tree is a binary search tree (BST).
def is_bst(root, min_val=float('-inf'), max_val=float('inf')):
    if root is None:
        return True
    if not (min_val < root.key < max_val):
        return False
    return is_bst(root.left, min_val, root.key) and is_bst(root.right, root.key, max_val)

# Output for Q6: Is the Binary Tree a Binary Search Tree? True

# Q7: Create a function to find the lowest common ancestor (LCA) of two nodes in a binary tree.
def lowest_common_ancestor(root, node1, node2):
    if root is None:
        return None
    if root.key == node1 or root.key == node2:
        return root
    left_lca = lowest_common_ancestor(root.left, node1, node2)
    right_lca = lowest_common_ancestor(root.right, node1, node2)
    if left_lca and right_lca:
        return root
    return left_lca if left_lca else right_lca

# Output for Q7: Lowest Common Ancestor of 5 and 15: 10
```
