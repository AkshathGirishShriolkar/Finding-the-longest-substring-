# Finding-the-longest-substring-

Find the lenght of the longest substring which consists of at most *k* number of characters and given string *s*. Note that uppercase and lowercase letters are considered different characters and spaces are not considered as characters at all.

**eg:**          s='leetcode' k=2.

**answer:** "lee" or "eet" .Since each string has only 2 unique characters but is the longest substring in the given string which has 2 characters.

## Input Format

- s= a string, k= an integer

# Output Format

- n where n is an integer

# Constraints

- 0 <= s.length < 10^6
- 0 <= n < 10^6

## Testcases

- Input:
   
   ```
   s='onomotopia', k=3
   ```
   
- Output:
   
   ```
   5
   ```
---
  
- Input:
   
   ```
   s='illustrated', k=4
   ```
   
- Output:

   ``` 
   5
   ```
---

- Input:
   
    ```
   s='alcoding', k=1
    ```
   
- Output:

   ``` 
   1
   ``` 
---

- Input:

   ```
   s='olaminion', k=3
    ```
   
- Output:

   ```
   5
   ```
---

- Input:

   ```
   s='eceba', k=2
   ```
   
- Output:

   ```
   3
   ```
---
   
- Input:

   ```
   s='fragile', k=0
   ```
   
- Output:

   ```
   0
   ```
---

- Input:

   ```
   s='DEEPseek', k=3
    ```
   
- Output:

   ```
   4
   ```
---

- Input:

   ```
   s='You are already dead', k=8
   ```
   
- Output:

   ```
   16
   ```




## Solution

- We use a sliding window approach for the above problem statement.
- In the function, before we go to the main fpart of the program, we 1st remove all the spaces.
- We then take care of the edge cases mainly (k=0 and s='')
- Next, we create 3 free variables. l (or) leng stores length of the string and end is the end pointer of the sliding window.
- Start is the start pointer of the sliding window.
- We start iterating through the string using a for loop.

- We enter the while loop with an appropriate condition.
- When the end pointer moves forward, block1 takes care of logging the character if the character is not present in the window
- Block2 takes care of when the number of unique characters in the window increases the value k. then, we exit the while loop and by doing that, we increase the start variable, essentially decreasing the sliding window's width by 1 from the left side
- Block3 just logs the length of the sliding window

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
            #block1
            if string[end-1] not in set1:
                set1.add(sstring[end-1])
                d[string[end-1]]=0
            d[string[end-1]]=d[string[end-1]]+1

            #block2
            if (set1).length>k:
                d[string[start]]=d[string[start]]-1
                if d[string[start]]==0:
                    set1.remove(string[start])
                if count<end-start-1:
                    count=end-start-1
                set1.remove(string[end-1])
                d[string[end-1]]=0
                break

            #block3
            if count<end-start:
                count=end-start
            end+=1
    return count
 ```

### Implementation

```
def alcoding(s,k):
    array_with_split_s=s.split()
    s=[]
    for i in array_with_split_s:
        s+=i
    if len(s)==0:
        return 0
    if k==0:
        return 0
    set1=set()
    set1.add(s[0])
    d=dict()
    d[s[0]]=0
    l=len(s)
    count=0
    j=1
    for i in range(l):
        if j==l:
            return count
        while j<=l:

            #block1
            if s[j-1] not in set1:
                set1.add(s[j-1])
                d[s[j-1]]=0
            d[s[j-1]]=d[s[j-1]]+1

            #block2
            if len(set1)>k:
                d[s[i]]=d[s[i]]-1
                if d[s[i]]==0:
                    set1.remove(s[i])
                if count<j-i-1:
                    count=j-i-1
                set1.remove(s[j-1])
                d[s[j-1]]=0
                break

            #block2
            if count<j-i:
                count=j-i
            j+=1
    return count
s=input()
k=int(input())
print(alcoding(s,k))
```
