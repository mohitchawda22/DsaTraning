##Binary Search using Ittirative processes.

```
arr=[1,2,3,4,5]
target=4
def BinarySearch(arr,low,high,target):
    while low<=high:
        mid=low+(high-low)//2
        if arr[mid]==target:
            return mid
        elif arr[mid]>target:
            high=mid-1
        else:
            low=mid+1
    return -1
    
result=BinarySearch(arr,0,len(arr)-1,target)
print(result)

```