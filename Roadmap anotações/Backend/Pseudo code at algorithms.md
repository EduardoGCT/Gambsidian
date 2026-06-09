
```
1
for i = 2 to n

2
key = A[i]


3
// Insert A[i] into the sorted subarray A[1 : i – 1].


4
j = i – 1


5
while j > 0 and A[j] > key


6
A[j + 1] = A[j]


7
j = j – 1


8
A[j + 1] = key
```
