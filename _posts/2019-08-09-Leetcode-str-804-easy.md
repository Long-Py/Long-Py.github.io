---
layout: post
title: '804. Unique Morse Code Words'
subtitle: ''
date: 2019-08-09
categories: Leetcode
tags: Leetcode Strings
---
### [804\. Unique Morse Code Words](https://leetcode.com/problems/unique-morse-code-words/)

Difficulty: **Easy**

Topics: **String**

International Morse Code defines a standard encoding where each letter is mapped to a series of dots and dashes, as follows: `"a"` maps to `".-"`, `"b"` maps to `"-..."`, `"c"` maps to `"-.-."`, and so on.

For convenience, the full table for the 26 letters of the English alphabet is given below:

```
[".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."]
```

Now, given a list of words, each word can be written as a concatenation of the Morse code of each letter. For example, "cba" can be written as "-.-..--...", (which is the concatenation "-.-." + "-..." + ".-"). We'll call such a concatenation, the transformation of a word.

Return the number of different transformations among all words we have.

```
Example:
Input: words = ["gin", "zen", "gig", "msg"]
Output: 2
Explanation: 
The transformation of each word is:
"gin" -> "--...-."
"zen" -> "--...-."
"gig" -> "--...--."
"msg" -> "--...--."

There are 2 different transformations, "--...-." and "--...--.".
```

**Note:**

*   The length of `words` will be at most `100`.
*   Each `words[i]` will have length in range `[1, 12]`.
*   `words[i]` will only consist of lowercase letters.


#### Solution

Language: **Python**

```python
class Solution(object):
    def uniqueMorseRepresentations(self, words):
        """
        :type words: List[str]
        :rtype: int
        """
        d = [".-","-...","-.-.","-..",".","..-.","--.","....","..",".---","-.-",".-..","--","-.","---",".--.","--.-",".-.","...","-","..-","...-",".--","-..-","-.--","--.."]
        
        return len(set("".join(d[ord(c)-ord('a')] for c in word) for word in words))
```

#### Notes
- **list comprehension**
- Be careful the **order** of two _for loops_