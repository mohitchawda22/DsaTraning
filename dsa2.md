## next greater elements 1
```
def next_greater_element(nums1, nums2):
    next_greater = {}
    stack = []

    for num in nums2:
        while stack and num > stack[-1]:
            next_greater[stack.pop()] = num
        stack.append(num)

    while stack:
        next_greater[stack.pop()] = -1

    return [next_greater[num] for num in nums1]
```

##Q.20. Valid Parentheses

```
class Solution:
    def isValid(self, s: str) -> bool:
        stack=[]
        for i in s:
            if i=='{' or i=='(' or i=='[':
                stack.append(i)
                
            elif stack and ((i == '}' and stack[-1] == '{') or 
                            (i == ')' and stack[-1] == '(') or 
                            (i == ']' and stack[-1] == '[')):
                stack.pop()
            else:
                 return False
        if not stack:
            return True
        else:
            return False 
```

##Q.2073. Time Needed to Buy Tickets

```
class Solution(object):
    def timeRequiredToBuy(self, tickets, k):
        """
        :type tickets: List[int]
        :type k: int
        :rtype: int
        """
        time = 0
        for i in range(len(tickets)):
            if i <= k:
                time += min(tickets[i], tickets[k])
            else:
                time += min(tickets[i], tickets[k] - 1)
        return time

```

##387. First Unique Character in a String.

```
class Solution(object):
    def firstUniqChar(self, s):
        """
        :type s: str
        :rtype: int
        """
        for i in range(len(s)):
            if s[i] not in s[:i] + s[i+1:]:
                return i 
        return -1 
        
```

##Q.503. Next Greater Element II

```
class Solution(object):
    def nextGreaterElements(self, nums):
        n = len(nums)
        ans = [-1] * n  # Initialize the result array with -1
        stack = []  # This will store indices

        # Traverse the array twice to handle the circular condition
        for i in range(2 * n):
            while stack and nums[stack[-1]] < nums[i % n]:
                # Update the result for the index at the top of the stack
                ans[stack.pop()] = nums[i % n]
            if i < n:
                stack.append(i % n)
        
        return ans
```
##2487. Remove Nodes From Linked List

```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def removeNodes(self, head: Optional[ListNode]) -> Optional[ListNode]:
        stack = []
        current = head

        # Traverse the linked list
        while current:
            while stack and stack[-1].val < current.val:
                stack.pop()
            stack.append(current)
            current = current.next

        # Reconstruct the linked list
        for i in range(len(stack) - 1):
            stack[i].next = stack[i + 1]
        stack[-1].next = None

        return stack[0] if stack else None
```