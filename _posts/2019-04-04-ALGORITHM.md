```python
M1 = [12,70,30,20,55,25,40,50]

def bublesort(matrix):
    
    for i in range(0,len(matrix)):
        for j in range(0,len(matrix)-1):
            if matrix[j+1]<matrix[j]:
                tmp = matrix[j]
                matrix[j] = matrix[j+1]
                matrix[j+1] = tmp
                print("MATRIX :: ",i,matrix)
    print("===================================================")
    print("RESULT ::    ",matrix)

def merge(left,right):
    result = []
    while len(left) > 0 or len(right) > 0:
        if len(left) > 0 and len(right) > 0:
            if left[0] <= right[0]:
                result.append(left[0])
                left = left[1:]
            else:
                result.append(right[0])
                right = right[1:]
        elif len(left) > 0:
            result.append(left[0])
            left = left[1:]
        elif len(right) > 0:
            result.append(right[0])
            right = right[1:]
    return result

def mergesort(matrix):
    
    if len(matrix) <= 1:
        return matrix
    mid = len(matrix)//2
    left = matrix[:mid]
    print("Left : ",left)
    right = matrix[mid:]
    print("Right : ",right)
    left = mergesort(left)
    right = mergesort(right)
    return merge(left,right)

print("Original Matrix : ",M1)
print("Merge Sorted : ", mergesort(M1))    
```
SORT ALGORITHM STUDY
