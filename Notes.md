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

### 7/17/2024

！[2024-7-17](./img/2024-07-17.png)

thoughts1: 

maintain a window for each leaf node. store the path of previous leaf node in some structure. when facing new leaf node, compare to all path in the structure to find good leaf pairs.\
runtime = traverse(n)*len(path)(lgn)*len(structure)(n). one solution is calculate the distance in O(1), or try to delete some far away leaf node that is no longer usable.

thoughts2:

find all leaf node in one stack. track their depth. if two node depth differs more than distance, then they have no chance to be good.\
runtime: find leaf = o(n), compare is 2^distance likely to n\
can we have more cleaver method to determine if some node is no need to maintain in stack?\
distance >= 2+|depth difference of their parents|\
any traversal that expands from some center? 

Final thought:

traverse through each node, keep a dictionary holding the number of leaves at depth x below this node. When a node have leaves on both left and right side, check whether there is any satisifying leaves.

**for a tree issue, using recurring is always the first thought to solve problem in O(n)**