### Arrays and Hashing


```python
def contains_duplicate(nums):
    hashSet = set()
    for n in nums:
        if n in hashSet:
            return True
        hashSet.add(n)
    return False

print(contains_duplicate([1,2,3,4]))
print(contains_duplicate([1,2,3,1]))
```

    False
    True
    


```python
def isAnagram(s, t):
    if len(s) != len(t):
        return False
    countS, countT = {}, {}
    for i in range(len(s)):
        countS[s[i]] = 1 + countS.get(s[i], 0)
        countT[t[i]] = 1 + countT.get(t[i], 0)
    for c in countS:
        if countS[c] != countT.get(c, 0):
            return False
    return True

print(isAnagram('anagram','anagram'))
print(isAnagram("rat", 'car'))
```

    True
    False
    


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python
def lengthOfLongestSubstring(s):
    charMap = {}
    left = 0
    maxLength = 0
    for right in range(len(s)):
        if s[right] in charMap:
            left = max(left, charMap[s[right]] + 1)
        charMap[s[right]] = right
        maxLength = max(maxLength, right - left + 1)
    return maxLength
print(lengthOfLongestSubstring(s = "abcabcbb"))
print(lengthOfLongestSubstring(s = "bbbbbbb"))
```

    3
    1
    


```python
def valid_palindrom(s):
    filtered_chars = [char.lower() for char in s if char.isalnum()]
    left, right = 0, len(filtered_chars) - 1
    while left < right:
        if filtered_chars[left] != filtered_chars[right]:
            return False
        left, right = left + 1, right - 1
    return True
s = "A man, a plan, a canal: Panama"
print(valid_palindrom(s))
```

    True
    
