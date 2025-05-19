## EX 3D Pattern Matching
## DATE: 29/03/25

## AIM:
To write a python program to implement pattern matching on the given string using Brute Force algorithm.

## Algorithm
1. Let s1 be the main string and s2 the pattern to search.

2. For each position i from 0 to len(s1) - len(s2):

3. Compare characters of s2 with the corresponding substring in s1 starting at i.

4. If all characters match:

5. Return the starting index i.

6. If no match is found after all positions are checked:

7. Return -1.

## Program:
Program to implement the Pattern Matching.

Developed by: Vidhyasri k

Register Number: 212222230170

```
def BF(s1,s2):
    len_s1 = len(s1)
    len_s2 = len(s2)

    for i in range(len_s1 - len_s2 + 1):
        j = 0
        while j < len_s2 and s1[i + j] == s2[j]:
            j += 1
        if j == len_s2:
            return i

    return -1
if __name__ == "__main__":
    a1=input() 
    a2=input() 
    b=BF(a1,a2)
    print(b)
```

## Output:
![image](https://github.com/user-attachments/assets/9a94254c-0e16-4280-8847-322caf6c244f)


## Result:
The brute force substring search program executed successfully and returned the starting index of the match or 0 if no match was found.
