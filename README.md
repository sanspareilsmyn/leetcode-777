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

56. Find K Closest Elements
- I did it by finding target index and adding left & right. But this needs improvement in efficiency.
- Use sliding window technique. return low ~ low+k

57. Valid Perfect Square
- Easy Binary Search with lower/upper bound.

58. N-ary Tree Preorder Traversal
- Care that children is list.

59. N-ary Tree Postorder Traversal
- Had a little trouble setting orders.

60. N-ary Tree Level Order Traversal
- I used tuple with (val, level). Maybe using dictionary(hash) might be more efficient.

61. Maximum Depth of N-ary Tree
- Had problem on helper function. Just used DFS.

62. Binary Search Tree Iterator
- I made inorder function and passed but efficiency was very low.

63. Insert into a Binary Search Tree
- Not difficult. Just had a little trouble at assigning new node.

64. Delete Node in a BST
- I knew how to make a logic, but didn't work at deleting node and synchronizing with original tree.
- The reason the node wasn't remove was that I didn't use recursive function to handle original node pointer.
- It doesn't matter we use rightmost node of left child or leftmost node of right child.
- Very important. Check it out again later.

65. Kth Largest Element in a Stream
- I used internal sort algorithm. How about not using it?
- Using priority queue. (Check how to use heapq library)
- Using priority queue is much efficient in finding k-th value in unordered array than sorting array itself!!!

66. Lowest Common Ancestor of a Binary Search Tree
- Because it's BST, we can compare max(p.val, q.val) / min(p.val, q.val) with root.val

67. Contains Duplicate III
- Simple loop makes timeout.
- I tried to use priority queue but failed.
- This is bucket sort algorithm.

68. Implement Trie (Prefix Tree)
- I had even no clue how to make an initiator.

69. Map Sum Pairs
- This was difficult to initiate the node.

70. Design HashSet
- Without built-in hash table libraries.
- I used the range of key and used modular calculation to define size of hashset.

71. Design HashMap
- What is difference btw HashSet & HashMap?
- HashSet has only one value. HashMap has (key, value).
- Something wrong with hash size or sth.
- I had to use extra ListNode.

72. Contains Duplicate
- Easy Dictionary problem.
- We could also use set(this is also hash table) and length of it.

73. Single Number
- If you add all nums and check value == 1, it's 2n calculation.
- If you delete hash if it exists, it's n calcuation.

74. Intersection of Two Arrays
- Easy set problem.

75. Happy Number
- Difficult in approach. Spent 10 mins and no clue. Checked answer.
- Calculate and return False if infinite loop found. It was brute-force way.

76. Two Sum
- Used hash table and found target - val technique.

77. Isomorphic Strings
- Made hash[char] = idx and tried to compare.

78. Minimum Index Sum of Two Lists
- Used hash table of index and used set - intersection.

79. Intersection of Two Arrays II
- I used intersection and count to append in answer list.

80. Contains Duplicate II
- Corner case! if k == 0? Passed but not efficient.

81. Group Anagrams
- Even though hashval is same, maybe char might not be same. How to handle it?
- How to handle hash collision?
- First, Seperate Chaining. Use Linked List as a node.
- Second, Open addressing. No need to use extra memory like Linked List. Use empty memory in hash table.
- I didn't have to used sum of ord as key. You could also use tuple ('a', 'c', 'e') as a key.

82. Find Duplicate Subtrees
- I think my method is right. Make hash table and add [node.left, node.right] & Add to answer if it already exists.
- My solution didn't catch root with children.

83. Jewels and Stones
- Very easy dictionary problem.

84. Longest Substring Without Repeating Characters
- First I iterated the string only once but that's not right.
- You have to iterate len(s) times to check it until same char comes out.
- Much efficient way is that you remember the index of previously appeared letter and use it.
- Very important question.

85. 4Sum II
- I tried to make hash with idx, make combination and check if there's element in all list.
- My original thought was not wrong. Make dict of AB Sum and CD Sum and make 0.

86. Top K Frequent Elements
- Easy with using zip, lambda.

87. Insert Delete GetRandom O(1)
- I did it with using dictionary.

88. Find Pivot Index
- I made it with slicing but very slow runtime.
- Think of it as a balance. Move weight to other. Don't calculate everytime.

89. Largest Number At Least Twice of Others
- Easy. But memory efficiency was not good.

90. Plus One
- Easy ''.join handling question.

91. Diagonal Traverse
- This is not n x n. It's m x n.
- Order is important when extending.

92. Spiral Matrix
- I was getting trouble in handling m, n = 1 case.
- Damn there was a one-liner. Like peeling apple, rotate and pop(0) upper line.
- Matrix rotation : Transpose and reverse order

93. Longest Common Prefix
- I really had trouble figuring out about idx. But it's easy.
- Use zip function!

94. Array Partition I
- Sort and add odd index.

95. Two Sum II - Input array is sorted
- With my method, I can't handle if target is negative.
- I used binary search.

96. Minimum Size Subarray Sum
- Found least maximum element index and incremented the size of subarray.
- I thought I'm right but didn't work on specific cases. Maybe I'm missing some conditions.
- You can't sort it. In other words, you can't change the order of array.
- Second approach. Find most closest index and slide window left and right.

97. Reverse Words in a String
- Easy split question.

98. Reverse Words in a String III
- Easy.

99. Design Circular Queue
- Review basic theory of circular queue.
- Reviewed how to handle front & rear pointer at empty case.

100. Number of Islands
- Classic. Tricky because grid element was "1", not "0".

101. Open the Lock
- I don't understand how to change 4 digits & filtering deadends.
- Very similar to 2D matrix. Think deeply of its idea.
- I made it again but time-out. Because of range(-1, 1). It should be (-1, 1).
- Important! If you have to find element, use set(hash). Don't use list. Same logic. Totally different result with list vs set!!!
- Why BFS? Why Not DFS? : If you use DFS, totally wrong. It's not minimum change count.

102. Perfect Squares
- I did it. Perfectly understood the logic of BFS. But memory usage is terrible. What's the better way?
- This can be solved with DP, not BFS. Its efficiency is better.

103. Min Stack
- Priority queue? No this is stack. Just use O(1) Memory.

104. Daily Temperatures
- I solved test case in two implementations but both time-outed. Maybe problem in logic itself.
- What's the difference btw my method and solution?
- I did it by creating list starting with current idx and literally iterated until finding larger one.
- Solution didn't find answer one by one. If next one is smaller than current one, just put in stack. If larger, pop all relevant indexes.

105. Evaluate Reverse Polish Notation
- I did it in one chance. Used number stack and using calcuator function.

106. Clone Graph
- I did it. Quite difficult but can handle it with DFS and set.

107. Decode String
- I had problem handling with numbers(especially '0'). Because numbers are also saved in str form.
- I handled original string into list while handling numbers. Then I used my original logic.
- Be careful. When numbers are given in str format, you have to take care of digits.

108. Flood Fill
- Simpel DFS with 2D Map.

109. 01 Matrix
- I struggled for a long time but couldn't handle it.
- Solution : Add 0 points at queue, visited. Pop zeroes and make + 1

110. Keys and Rooms
- I confused about making visited list.
- This doesn't use visited. Cause it can enter the room again.
- Don't think of it as literally visiting once at a time, just collect every possible key next to curr.
- I tried to collect keys but failed to step before.
- Problem was so easy but I didn't understand it properly. I didn't have to move once at a time!

111. 3Sum
- Used combinations but had to filter things that have same element. Timeout.
- Special Method needed. How about binary search?
- I implemented it but didn't properly iterate the index. But I think I can handle it soon.
- I used binary search method and used mid pointer but solution used two pointers and +1 and -1.
- Important point! You shouldn't use break. You have to check every possibility on starting i.

112. Best Time To Buy And Sell Stock II
- Not difficult. Just sell every time when you can earn profit. Greedy approach.
- Can be solved with DP. I need DP Training.

113. Set Matrix Zeroes
- I changed all with BFS. We have to control where we gonna stop.
- I added count variable. This doesn't work well.
- Concentration and mistakes!
- Didn't have to solve with BFS. Just use marker zero rows [None] * size and check it and transform it. O(m+n).

114. Rotate Array
- Pop and insert method (Method 1)
- Slicing (Method 2)
- Reverse method is really good. If you want k = 3, Reverse whole list -> Reverse [0:3] -> Reverse [3:]

115. Longest Palindromic Substring
- First I used Brute-Force method. Compared every possible strings. Timeout.
- What is possible? Hash table of characters? I used combinations and hash of characters. Success! But it can be improved.
- Use helper function that compares inner and outer. Both odd and even cases.

116. Rotate Image
- I learned it before. Trasnposing and Reverse.
- Why doesn't it work? Result is right but it doesn't apply to result.

117. Increasing Triplet Subsequences
- First I was supposed to do Brute-Force (O(n^2)).
- Second I tried it by DP. (O(n)) This didn't work. This is just a index 0 case of Brute-Force.
- Solution used first, second memory and initialized it as float('inf').

118. Reverse Integer
- Logic is easy. But

119. Add Two Numbers
- I did it with dummy node and [::-1] but efficiency was terrible.
- I didn't have to literally calculate everything. I could just implement add and carry.
- I learned how to use divmod. It returns // and %.
- Don't make seperate loop for l1, l2 and carry. Go together.

120. First Unique Character in a String
- Inserting Hash : O(n), Iterating Hash : O(n). Is there better way than this?
- I learned how to use collections.Counter.

121. Odd Even Linked List
- Use Dummy Node Technique. How to well handle changing node pointer?
- I did it. Controlling and holding pointer is difficult.

122. Valid Anagram
- Use Counter. Life is easy.

123. Valid Palindrome
- If you want to use regex, use re.compile(condition) & re.findall(string)!

* DP
124. Unique Paths
- Classic DP Problem with memoization. Make ans map with same size of original map. Do summation.

125. Unique Paths II
- Similar but don't initialize if there's obstacle.

126. Minimum Path Sum
- Easy.

127. Decode Ways
- Very difficult to think of idea.
- I figured out how to solve it. First, save 0 ~ 9. If something comes more, it's only possible if it combines with one with before.
- Difficult. I got it with solution. Try it again.

128. Unique Binary Search Trees
- Almost impossible to think of rules if you don't know it priorly.
- Suppose you have i on the node. Then, 1 ~ (i-1) will be at the left and (i+1) ~ n will be at the right.
- Use this and make DP. Brilliant.

129. Interleaving String
- I just tried to pop in an order but it doesn't be removed in order.
- I used while loop but don't know where to stop if it's False.

130. Majority Element
- Easy hash table question.

131. ZigZag Conversion
- Easy with making index list.

132. Excel Sheet Column Number
- This is 26-digit number counting. Easy.

133. 4Sum
- Combinations => timeout.
- This is so so difficult.

134. Factorial Trailing Zeroes
- Factorize and count 2, 5. return min count of 2 & 5.
- Use that 5 is always more than 2.

135. Divide Two Integers
- I just kept minusing with careful treat of +, -.
- It accelerated minusing by multipling divisor.
- Learned how to handle 32 bit integer overflow condition.

136. Reverse Bits
- Didn't know how to handle binary string.

137. Next Permutations
- I don't know how to approach it. How about Brute Force? This will be definitely timeouted.
- Use two steps. First, figure out where first ascending comes from the back. Next, find which element is larger than target from the back. Third, reverse it.

138. Remove Linked List Elements
- Use dummy node. Having trouble handling same element case.
- We could just use single pointer.

139. Find First and Last Position of Element in Sorted Array
- Binary Search? Yes. But efficiency was not that good.

140. Count Primes
- Easy. Make 2, 3 as standard and use modular calculation.
- This is "Less than" question.
- Time outed. What's the efficient algorithm for finding prime numbers?
- Prime Number == Sieve of Eratostenes! Use DP.

141. Count and Say
- I used count function. I think I misunderstood the question. Try again!
- I did it as rule based counting. What's other creative way to solve it?

142. Implement Stack using Queues
- Easy.

143. Combination Sum
- DFS. But duplication issue. Not efficient.

144. Invert Binary Tree
- DFS right. I think I'm close but little bit tricky.
- I understood. You had to draw the tree.

145. Combination Sum II
- I made a logic similar to Combination Sum but timeout. Need to find efficient way.
- Technique : skip the same element by nums[i] == nums[i-1].

146. Summary Ranges
- I have trouble setting pointers.
- Finally did it by myself.

147. Multiply Strings
- Not that difficult. Use pow(10) calculations.

148. Power of Two
- I thought it too simple way. Of course if ends in 2, 4, 6, 8 but 6 is not power of 2!.
- How about memoization? Time outed.
- Bit manipulation! 1000(8) & 0111(7) should be zero!.

149. Jump Game II
- Greedy? DFS?
- I used greedy but having trouble returning value.
- I think I didn't understand the condition well. (On len(nums) == 1)
- This is quite tricky but good question.

150. Palindrome Linked List
- With O(n) time complexity and O(1) space complexity!
- Very difficult technique. You have to reverse first half.

151. Permutation II
- I did it at just one trial. Using DFS is key to permutation. This is not efficient. use nums[i] == nums[i-1].

152. Binary Tree Paths
- DFS? Easy.

153. Jump Game
- Greedy. I had same trouble when solving II.
- Succeeded but efficiency is terrible.
- We can go back and check whether we arrive at zero.

154. Add Digits
- Do it without any loop/recursion in O(1) runtime?
- I used loop and it was right.

155. Merge Intervals
- Greedy. I didn't properly handle range.
- Very good question. I did it. Key is to sort with starting point.

156. Ugly Number
- Used while loop and modular.

157. Insert Interval
- Easy. Append, sort and merge.

158. Missing Number
- Had trouble handling corner cases.
- But my idea was right. Sum - numsum.

159. Spiral Matrix II
- How to spin left 90 degree?
- I misunderstood the question.
- In reverse, start with zero matrix and stop when it becomes full.

160. Word Pattern
- Corner cases. Be careful! You should always think of all possible cases before submitting.

161. Rotate List
- I just did it by calculate length and moving pointers directly.
- I think my solution is better.

162. Nim Game
- DP? Greedy?
- I used DP but memory error. I can't assign that big list. Have to solve it recursively.
- Used Recursion but wrong.
- You win if n % 4 != 0. This is like a brain-teaser.

163. Simplify Path
- I understood. Simple up down counting doesn't work. Cause .. doesn't mean anymore if already in root.
- I did it. This is stack question.

164. Range Sum Query - Immutable
- Easy.

165. Search a 2D Matrix
- Corner cases. What if target is larger than matrix maximum? What if row length is 1?

166. Power of Three
- Easy with while loop.

167. Sort Colors
- Why not quick sort? I always forget how to implement quick sort.
- Quick sort!

168. Power of Four
- Easy.

169. Combinations
- I did it as usual with dfs but timeout.
- How about only using cand[i+1:]?

170. Reverse Vowels of a String
- Capital letter... not a good question.

171. Subsets
- Easy backtracking similiar with Perm, Comb.

172. Ransom Note
- First, Brute Force is possible. Any better way?
- No this is not string match. This is hash table problem.
- Using counter is the best way.

173. Word Search
- BFS. Memory Limit Exceeded. My logic should be modified.
- Check solution. DFS with clean code. Memorize it.

174. Find the Difference
- Easy. Sort and compare.

175. Remove Duplicates from Sorted Array II
- This is tricky and complicated.

176. Is Subsequence
- Tricky. Two Pointer technique.

177. Search in Rotated Sorted Array II
- Make it right in order and binary search.

178. Sum of Left Leaves
- I have trouble returning final value.
- Did it with BFS.

179. Remove Duplicates from Sorted List II
- Two pointer. Almost right.
- Had to use Three pointer.

180. Convert a number to Hexadecimal
- Let's do it with/without library.
- I think it's important question.
- If you have to use 2's Complement, add overhead num to original number.

181. Partition List
- Used two pointer.

182. Longest Palindrome
- I thought adding all even numbers and add maximum odd number. But my logic was wrong.
- Odd number can be used! minus one!

183. Gray Code
- Make all possible set and change it to int.
- How do we implement Gray Code?
- Bit Manipulation.

184. Subsets II
- When do we have to finish backtracking?
- My memory usage was terrible.

185. Fizz Buzz
- So easy

186. Reverse Linked List II
- Reversing is difficult technique. Master it today.

187. Add Strings
- Without converting to integer.
- Make list -> Reverse -> Add -> Treat Carry -> Join.

188. Restore IP Addresses
- Choosing three points and check possibilities.
- Handling 0 cases was tricky & Timeout for len(s) > 17.
- Solution used Backtracking.

189. Number of Segments in a String
- Not a good question. Use a stack

190. Unique Binary Search Trees
- I remember how to do it.

191. Unique Binary Search Trees II
- Recursion? Very difficult. GG.

192. Arranging Coins
- Easy.

193. Interleaving String
- Very Difficult. I didn't even realize this was dp problem.
- With DFS.

194. Binary Tree Zigzag Level Order Traversal
- I did it with making with_level array.

195. Convert Sorted List to Binary Search Tree
- Select mid point, make then.
- Techinique -> How to get pointer on half of Single Linked List.

196. Path Sum II
- Backtracking. Did it but very inefficient.
- I used sum calculation for every iteration. This is not good.

197. Flatten Binary Tree to Linked List
- Very difficult recursion question.

198. Triangle
- DP.

199. Sum Root to Leaf Numbers
- Easy DFS. 
