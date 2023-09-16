TOPIC : [[ARRAYS AND HASHING]]
`2023-07-09

## TOPIC INFO 
ok so basically the question is to design a encoder and a decoder algorithm that can take in a list of strings and encode it into a single string and vice a versa 

so how do we do it ... the first thought is to use just a symbol to signify the end of a word in the string but the catch is that all the characters are accepted therefore we cant just use a character to do this

now this gives us an idea to somehow encode the lengths of the word in the string soo every first integer i the lenght of the next word and we read it for that many letters now the solution online said that we also need to add a delimiter for the same but i dont see the read to do that so i dont.

```python

    def encode(self, strs):
        res = ""
        for s in strs:
            res += str(len(s)) + "#" + s
        return res

    """
    @param: s: A string
    @return: decodes a single string to a list of strings
    """

    def decode(self, s):
        res, i = [], 0

        while i < len(s):
            j = i
            while s[j] != "#":
                j += 1
            length = int(s[i:j])
            res.append(s[j + 1 : j + 1 + length])
            i = j + 1 + length
        return res
```


### BRIEF



### CONCLUSION