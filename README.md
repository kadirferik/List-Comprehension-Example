# List-Comprehension-Example
```
import itertools
import numpy as np
if __name__ == "__main__":
    x = int(input())
    y = int(input())
    z = int(input())
    n = int(input())
    i = []
    j = []
    k = []
    set1 = set()
    coordinate = []
    coordinate1 = []
    coordinate2 = []
    for q in range(x+1):
        i.append(q)  
    for q in range(y+1):    
        j.append(q) 
    for q in range(z+1):
        k.append(q)  
    if x == y ==z:
        for b in range(x+1):
            coordinate.append([i[b], j[b], k[b]])
            coordinate.append([0, j[b], k[b]])
            coordinate.append([i[b], 0, k[b]])
            coordinate.append([i[b], j[b], 0])
    elif (x < y < z) or (x < z < y):
        for b in range(x+1):
            coordinate.append([i[b], j[b], k[b]])
            coordinate.append([0, j[b], k[b]])
            coordinate.append([i[b], 0, k[b]])
            coordinate.append([i[b], j[b], 0])
    elif (y < x < z) or (y < z < x):
        for b in range(y+1):
            coordinate.append([i[b], j[b], k[b]])
            coordinate.append([0, j[b], k[b]])
            coordinate.append([i[b], 0, k[b]])
            coordinate.append([i[b], j[b], 0])
    elif (z < x < y) or (z < y < x):
        for b in range(z+1):
            coordinate.append([i[b], j[b], k[b]])
            coordinate.append([0, j[b], k[b]])
            coordinate.append([i[b], 0, k[b]])
            coordinate.append([i[b], j[b], 0])
    for s in range(x+1):
        set1.add(i[s])
    for s in range(y+1):
        set1.add(j[s])
    for s in range(z+1):
        set1.add(k[s])
    coordinate.append(list(itertools.permutations(set1, 3)))
    for i in range(len(coordinate)):
        coordinate2 = list(coordinate[i])

    coordinate3 = np.array(coordinate2)
    for g in range(len(coordinate3)):
        if (coordinate3[g, 0] <= x) and (coordinate3[g, 1] <= y) and (coordinate3[g, 2] <= z):
            if ((coordinate3[g, 0] + coordinate3[g, 1] + coordinate3[g, 2]) != n):
                coordinate1.append(coordinate2[g])
    print(coordinate1)
