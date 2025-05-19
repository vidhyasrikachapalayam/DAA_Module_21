# EX 3B Hamiltonian Circuit Problem
## DATE: 22/03/25
## AIM:
To write a python program to check whether Hamiltonian path exits in the given graph.

## Algorithm
1. Initialize a DP table dp[node][mask]:

2. True if a path ending at node visits all nodes in mask.

3. Set base cases: dp[i][1 << i] = True for all nodes i.

4. For all subsets mask of nodes:

5. For each node j in mask:

6. For every node k in mask:

7. If there's an edge k → j and a valid path to k without j, then:

8. Set dp[j][mask] = True

9. After filling the DP table, check if any dp[i][(1 << N) - 1] is True.

10. If yes, Hamiltonian path exists.
 
## Program:
Program to implement to check whether Hamiltonian path exits in the given graph.

Developed by: Vidhyasri k

Register Number: 212222230170

```    
def Hamiltonian_path(adj, N):
    dp = [[False for _ in range(1 << N)] for _ in range(N)]

    for i in range(N):
        dp[i][1 << i] = True

    for i in range(1 << N):
        for j in range(N):
            if (i & (1 << j)) and any((i & (1 << k)) and adj[k][j] and j != k and dp[k][i ^ (1 << j)] for k in range(N)):
                dp[j][i] = True

    return any(dp[i][(1 << N) - 1] for i in range(N))
    
adj = [ [ 0, 1, 1, 1, 0 ] ,
        [ 1, 0, 1, 0, 1 ],
        [ 1, 1, 0, 1, 1 ],
        [ 1, 0, 1, 0, 0 ] ]
 
N = len(adj)
 
if (Hamiltonian_path(adj, N)):
    print("YES")
else:
    print("NO")
```
## Output:
![image](https://github.com/user-attachments/assets/f1215a5a-90a0-4f88-9463-3d8c155fab07)

## Result:
The Hamiltonian path program executed successfully, and it determined whether a Hamiltonian path exists in the given graph.
