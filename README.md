# 리트코드 도장깨기  
1. Max Consecutive Ones
- Comparison btw maxv & tmpv

2. Duplicate Zeros
- In-place operation
- Very Important to handle overwriting problem and to solve it by approaching from back, counting zeros well.

3. Merge Sorted Array
- Fill from the back with largest element. Fill Leftover automatically.

4. Remove Element
- In-place operation with O(1) extra memory.
- We must conside edge cases & corner cases!
- I solved it by counting # of deletion and changed the position in-place. But there might be better way.
- In Python, swap is automatically done. ex) a, b = b, a
- You can also use count & remove function.
- Using start, end pointer is very nice.

5. Remove Duplicates From Sorted Array
- Don't use start, end pointer way. It just messes up the ascending order. It's not the answer.
- We don't have to change. We just have to overwrite at the boundary.

6. Check If N and Its Double Exist
- Sort & O(n^2). Maybe better way.
- Sort and Binary Search for leftovers -> Failed because of negative numbers.

7. Valid Mountain Array
- I used upflag and downflag.
- Thinking of corner cases is very important. Test with every possibilities.
- 4 cases. Up/Down, Down/Up, Up, Down

8. Replace Elements with Greatest Element on Right Side
- If current value == current max, find again. Else, just use that value.
- The problem is to find maximum value from backward. We can reverse array and solve it too. This is more clear way.

9. Remove Duplicates from Sorted Array
- I've solved it before. Change the value if new value comes in by using counter. Return counter.

10. Move Zeroes
- I've solved it. But It's not efficient code. I just swapped the nearest value if current value is zero.
- I found another way. Just pop all 0 and count it. Later push back them.
- My first idea was valid. Remembering current zero position and using it.

11. Sort Array By Parity
- Similar with Move Zeroes. I used counter to bring parity number.

12. Remove Element
- Similar with Move Zeroes. I used counter. This is very useful to perform in-line operation.

13. Height Checker
- Sort and compare, count.

14. Third Maximum Number
- They only need distinct number. So change array into set and pop 2 max nums.
- If we can't delete elements, we have to make a list.

15. Find All Numbers Disappeared in an Array
- I tried by using set and checking one-by-one, but time-outed.
- This is amazing. We have to use value as an index to solve this problem.
- Make inverse of the number with value iteration.

16. Squares of a Sorted Array
- I just used sort & power. Maybe different way.

17. Design Linked List
- Difficulty at setting initial config. ex) class ListNode(), head, val, next, etc.

18. Linked List Cycle
- I tried to use fast & slow. But Nonetype Runtime Error happened.
- while fast is not None and fast.next, fast = fast.next.next / slow = slow.next
- This is start of two-pointer technique.

19. Linked List Cycle II
- I tried to use again fast, slow pointer. But it doesn't go well.
- One pointer waits. One pointer runs. If running pointer get ends, waiting pointer goes next. Until wating pointer get ends.
- But if we do this, if cycle exists, running pointer is in infinite loop.
- So let's use three pointers. Wait, Fast, Slow. But we can't say that fast==slow pointer is same as wait pointer.
- Answer : First, check cycle. Next, move head to figure out starting point.
- I couldn't understand why head should continuously move.
- This is the explanation. https://leetcode.com/problems/linked-list-cycle-ii/discuss/44793/O(n)-solution-by-using-two-pointers-without-change-anything

20. Intersection of Two Linked Lists
- From backward? But how? This is Single linked list.
- I don't know.
- Wow. Concatenate two list and find cycle is same as finding intersection. Find start of the loop like Linked List Cycle II.

21. Remove Nth Node From End of List
- I tried to use two pointer. Make distance of n and delete the proper one. But it didn't work well on short list.
- I was almost right. I had to move front pointer n times. If front is None, then head should be head.next. Else, move front/back and back.next = back.next.next

22. Reverse Linked List
- I solved it but it's too inefficient.
- Let's use two pointers. Prev & Curr.

23. Design Linked List (Double Linked List)
- Similar with #17

24. Merge Two Sorted Lists
- I solved it by moving with comparison, but I had troubles handling empty l1 or empty l2.
- We could use whole l1 or l2 if left!
- We didn't have to make new node & We had to use dummy node for efficiency and return dummy.next!

25. Binary Tree Preorder Traversal
- I had a problem how to save and return answer list.
- We can use DFS & stack to return list.
- I tried BFS (queue) but this didn't work well. Cause it should be depth-first on left node.
- I solve it again with approach of helper function used in Inorder/Postorder Traversal. It's much easier. Check it out on my submission.

26. Binary Tree Inorder Traversal
- Using helper function. Classic way.

27. Binary Tree Postorder Traversal
- Exactly same approach with Inorder traversal.

28. Binary Tree Level Order Traversal
- I solved it by using tuple(val, level). Maybe there is more efficient solution.

29. Maximum Depth of Binary Tree
- Just solve it recursively.

30. Symmetric Tree
- I had an idea but couldn't implement it properly.
- Classic recursive problem. Use another helper function.

31. Path Sum
- I knew how to handle it but had problem on returning bool.

32. Construct Binary Tree from Inorder and Postorder Traversal
- Very difficult. Maybe end of Postorder is head. 
- Think abstractly.

33. Construct Binary Tree from Preorder and Inorder Traversal
- Very similar with 32. Make map_inorder and make recur function.

34. Populating Next Right Pointers in Each Node
- I think this is very similar problem with Symmetric Tree problem.
- This solution is beautiful. https://leetcode.com/problems/populating-next-right-pointers-in-each-node/discuss/37465/Python-Solution-With-Explaintion
- I have to solve it again later.

35. Reverse String
- Easy. Use mid index. Maybe different
- We could use two pointers.

36. Swap Nodes in Pairs
- I will use helper function and start with root.
- Swap is complex. I know how to do but difficult to implement.
- We had to use "dummy node" to return starting point! What is the use of self?

37. Search in a Binary Search Tree
- I did it by recursive way.

38. Fibonacci Number
- So easy with memoization.

39. Pow(x, n)
- Use Tail-recursion!
- First I used classic recursive way. Why don't we also solve it in iterative way?
- We also had to consider negative n.

40. K-th Symbol in Grammar
- I reversed the string before but time-outed. Have to figure out another way.
- We didn't have to make all strings. There is a rule. Same rule that I found but didn't have to make all strings. This is beautiful.

41. Lowest Common Ancestor of a Binary Tree
- I splited 2 cases and almost solved it but time-outed.
- If root == p or q, we can just return root.
- I didn't have to make additional finder function. I could just use the body function itself.

42. Sort an Array
- Basic of basic. Must be expert on this.
- Reviewing Quick Sort. Main difficulty of Quick Sort in-place algorithm is that pivot index != partition index!

43. Validate Binary Search Tree
- I have a logic and clue but always have trouble on implementing how to return answer.
- Add order in inorder traversal and compare list.
- Compare left, right value with helper function.

44. Search a 2D Matrix II
- I tried to solve with simple DFS but time-outed. Have to use ascending property of matrix.
- I splited two case. Larger and smaller. But also time-outed.
- This map is special. Left one is smallest. Upper one is smallest. First find the row and find column.

45. Valid Sudoku
- Row, Column, Box check module.

46. Combinations
- I really wanted to solve this problem clearly before. Let's break it.
- We have to approach with DFS.
- Had some trouble with combining lists.

47. Permutations
- Similar with Combinations

48. Same Tree
- Why my solution is wrong? I left one condition. p.val == q.val. Silly mistake.

49. Generate Parentheses
- I think this is also backtracking dfs question. Use ( counter and ) counter.
- I just made all possible setups and created another checking module. Terrible efficiency.

50. Binary Search
- Had trouble finishing search but debugged with printing low, mid, high.

51. sqrt(x)
- I used binary search. For truncating, I returned low - 1 if low * low != x.

52. Guess Number Higher or Lower
- Easy Binary Search question.

53. Search in Rotated Sorted Array
- Modular calculation with pivot + Binary Search

54. First Bad Version
- Easy. Set mid as True & False intersection.

55. Find Peak Element
- Input is not sorted type one. Is it meaningful to use Binary Search in this case too?
- I solved it with Binary Search but efficiencty is terrible. (O(n))
- To apply BS, I had to understand 4 cases of peak condition.

