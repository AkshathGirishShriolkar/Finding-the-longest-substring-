# Finding-the-longest-substring-

Find the lenght of the longest substring which consists of at most *k* number of characters and given string *s*. Note that uppercase and lowercase letters are considered different characters and spaces are not considered as characters at all.

**eg:**          s='leetcode' k=2.

**answer:** "lee" or "eet" .Since each string has only 2 unique characters but is the longest substring in the given string which has 2 characters.

#Input Format

-s= a string, k= an integer

#Output Format

- n where n is an integer

#Constraints

-0 <= s.length < 10^6
-0 <= n < 10^6

## Testcases

1. Input:
   ```s='onomotopia', k=3```
1. Output:
   ```5```
  
2. Input:
   ```s='illustrated', k=4```
2.Output:
   ```5```

3. Input:
    ```s='alcoding', k=1```
3.Output:
   ```1```

4. Input:
   ```s='olaminion', k=3```
4. Output:
   ```5```

5. Input:
   ```s='eceba', k=2```
5. Output:
   ```3```
   
6. Input:
   ```s='fragile', k=0```
6. Output:
   ```0```

7. Input:
   ```s='DEEPseek', k=3```
7. Output:
   ```4```

9. Input:
   ```s='You are already dead', k=8```
9. Output:
   ```16```




##Solution

- we use a sliding window approach for the above problem statement.

###Implementation

