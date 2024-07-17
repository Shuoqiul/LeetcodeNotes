# Leetcode Notes for daily question

### 7/16/2024

![2024-7-16](./img/2024-07-16.png)

A standard question for tree traversal. \
My thoughts:\
From back to top. When I face a node to delete, if the subtree under the node is clear for deletion, then I can plainly delete this node and put the children into result.\
So by using recurrsion, I deal with the node value after visiting all its children. If the node is to be deleted, change the left/right pointer of its parent and move children nodes into result.

Time: each node enter once. O(n)\
Space: constant memory except output list. O(n)

Best time ver:\
First traverse the tree to build a dictionary between value and node. Add parent pointer for each tree node. Then plainly loop through the **to_delete** list and for each deletion change its parent and move children to result.

Time: First traversal O(n), then O(len(o_delete))
Space: O(n) for dictionary, O(n) for changing the original tree to add one more pointer.