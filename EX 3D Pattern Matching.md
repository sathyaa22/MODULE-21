# EX 3D Pattern Matching
## DATE: 25.04.2025
## AIM:
To write a python program to implement pattern matching on the given string using Brute Force algorithm.


## Algorithm
1. Start the program.
2. Read the input string Text and the pattern string Pattern.
3. Let n be the length of Text. Let m be the length of Pattern.
4. Set index i = 0.
5. Repeat these steps while i ≤ n - m:
   Set index j = 0.
   Repeat step 9 while j < m and Text[i + j] = Pattern[j]:
   Increment j by 1.
   If j = m, then the pattern is found at position i, so return i and stop.
   Increment i by 1.
6. If the loop completes without finding the pattern, return -1.
7. End the program.


## Program:
```
Program to implement the Pattern Matching.
Developed by: SATHYAA R
Register Number: 212223100052
```

```
def BF(s1,s2):
    n = len(s1)
    m = len(s2)
    
    for i in range(n - m + 1):
        j = 0
        while j < m and s1[i + j] == s2[j]:
            j += 1
        if j == m:
            return i
    return -1
    
if __name__ == "__main__":
    a1=input() 
    a2=input() 
    b=BF(a1,a2)
    print(b)
```


## Output:

![image](https://github.com/user-attachments/assets/95dd7dd7-8071-4ab3-bdaf-de9ef3f7c533)


## Result:
The brute force substring search program executed successfully and returned the starting index of the match or 0 if no match was found.
