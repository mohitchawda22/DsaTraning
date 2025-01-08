[**1. Two Sum**]

```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        for i in range(len(nums)-1):
            for j in range(i+1,len(nums)):
                if(nums[i]+nums[j]==target):
                    return(i,j)
              
```
##Time complexity of this code is -n^2


**1304. Find N Unique Integers Sum up to Zero**

```
class Solution:
    def sumZero(self, n: int) -> List[int]:
        arr=[]
        # if n==1:
        #     arr.append(0)
        #     return arr
        if(n%2!=0):
            arr.append(0)

        while(len(arr)<n):
            i=len(arr)+1
            arr.append(i)
            arr.append(-i)  
        return arr
        
```

##Time complexity is n


**53. Maximum Subarray**

```
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        maxSum=nums[0]
        currentSum=nums[0]

        for num in nums[1:]:
            currentSum=max(num,currentSum+num)
            maxSum=max(maxSum,currentSum)

        return maxSum

```
##Time complexity is n


### **Second Largest**

```
class Solution:
def getSecondLargest(self, arr):
# Code Here

    if len(arr)<=1:
        return -1
    l=-1
    l2=-1
    for i in range(len(arr)):
        if arr[i]>l:
            l2=l
            l=arr[i]
        elif arr[i]>l2 and arr[i]!=l:
            l2=arr[i]
    return l2

```

## Time complexity is n

**876. Middle of the Linked List**

```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
        slow=fast=head
        while fast and fast.next:
            slow=slow.next
            fast=fast.next.next
        return slow
```

## Time complexity is n

Search in Rotated Sorted Array
```
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        
        for i in range(len(nums)):
            if target == nums[i]:
                return i
        return -1
```

## Time complexity is n

35. Search Insert Position

```
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
        for i in range(len(nums)):
            if nums[i]==target or nums[i]>target:
                return i
        return len(nums)
```

## Time complexity is n

88. Merge Sorted Array

```
class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """
        for j in range(n):
            nums1[m+j]=nums2[j]
        nums1.sort()

```

# Time complexity is 2n 

32. Longest Valid Parentheses

```
class Solution:
    def longestValidParentheses(self, s: str) -> int:
        stack=[]
        stack.append(-1)
        max_len=0
        for i in range(len(s)):
            if s[i]=="(":
                stack.append(i)
            else:
                stack.pop()

                if not stack:
                    stack.append(i)
                else:
                    max_len=max(max_len,i-stack[-1])
        return max_len
```

## Time complexity is n

15. 3Sum

```

class Solution:
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        arr=[]
        for i in range(0,len(nums)-2):
            for j in range(i+1,len(nums)-1):
                for k in range(j+1,len(nums)):
                    if nums[i]+nums[j]+nums[k]==0:
                        arr.append([nums[i],nums[j],nums[k]])
                    j=j+1
                i=i+1
        return arr
                        
```

## Time complexity is n^3