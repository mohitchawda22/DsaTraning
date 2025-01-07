[**1. Two Sum**]

```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        for i in range(len(nums)-1):
            for j in range(i+1,len(nums)):
                if(nums[i]+nums[j]==target):
                    return(i,j)
```

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

### **Second Largest**

class Solution:
def getSecondLargest(self, arr):
# Code Here
# temp=[]
# for i in range(len(arr)-1):
#     temp.append(arr[i])
#     if arr[i+1]>temp[i]:
#         temp.pop(i)
#         temp.append(arr[i+1])
#         return temp

```
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

Search in Rotated Sorted Array
```
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        
        for i in range(len(nums)):
            if target == nums[i]:
                return i
        return -1
```

35. Search Insert Position

```
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
        for i in range(len(nums)):
            if nums[i]==target or nums[i]>target:
                return i
        return len(nums)
```