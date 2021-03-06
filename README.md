# leetcode-777
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
