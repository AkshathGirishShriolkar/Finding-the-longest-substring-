# Finding-the-longest-substring-

Find the lenght of the longest substring which consists of at most *k* number of characters and given string *s*. Note that uppercase and lowercase letters are considered different characters and spaces are not considered as characters at all.

**eg:**          s='leetcode' k=2.

**answer:** "lee" or "eet" .Since each string has only 2 unique characters but is the longest substring in the given string which has 2 characters.

## Input Format

-s= a string, k= an integer

# Output Format

- n where n is an integer

# Constraints

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

4. Input:
   
    ```s='alcoding', k=1```
   
3.Output:

   ```1```

5. Input:

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

8. Input:

   ```s='You are already dead', k=8```
   
8. Output:

   ```16```




## Solution

- we use a sliding window approach for the above problem statement.

```
def alcoding(s,k):
    array_with_split_s = split s wrt ' '
    string=new array of length s.length
    for i in array_with_split_s:
        string=string+i
    if string.length==0:
        return 0
    if k==0:
        return 0
    set1=set()
    set1.add(string[0])
    d=dict()
    dstring[0]]=0
    leng=string.length
    count=0
    end=1
    for start from 0 to leng:
        if end==l:
            return count
        while end<= leng:
            if string[end-1] not in set1:
                set1.add(sstring[end-1])
                d[string[end-1]]=0
            d[string[end-1]]=d[string[end-1]]+1

            if (set1).length>k:
                d[string[start]]=d[string[start]]-1
                if d[string[start]]==0:
                    set1.remove(string[start])
                if count<end-start-1:
                    count=end-start-1
                set1.remove(string[end-1])
                d[string[end-1]]=0
                break
            if count<end-start:
                count=end-start
            end+=1
    return count
 ```

### Implementation

