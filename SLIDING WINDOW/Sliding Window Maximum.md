TOPIC : [[SLIDING WINDOW]]
`2023-09-18

## TOPIC INFO 

You are given an array of integers `nums`, there is a sliding window of size `k` which is moving from the very left of the array to the very right. You can only see the `k` numbers in the window. Each time the sliding window moves right by one position.

Return _the max sliding window_.

**Example 1:**

**Input:** nums = [1,3,-1,-3,5,3,6,7], k = 3
**Output:** [3,3,5,5,6,7]
**Explanation:** 
Window position                Max
---------------               -----
[1  3  -1] -3  5  3  6  7       **3**
 1 [3  -1  -3] 5  3  6  7       **3**
 1  3 [-1  -3  5] 3  6  7      **5**
 1  3  -1 [-3  5  3] 6  7       **5**
 1  3  -1  -3 [5  3  6] 7       **6**
 1  3  -1  -3  5 [3  6  7]      **7**

so basically we have to find the max value in each sliding window ..


here my approach was a monotonic dec stack but ya like when you pop off elements you dont have track of the other elements which can be there .

So in the solution we have to use a decreasing Deque where when you add an element if the element is larger than the elements in the deque then we pop those elements off till it reaches the point where the element in the deque is either larger or same and the max for each phase of the sliding window is the first element in the deque .


```cpp
/*
    Given int array & sliding window size k, return max sliding window
    Ex. nums = [1,3,-1,-3,5,3,6,7] k = 3 -> [3,3,5,5,6,7]

    Sliding window deque, ensure monotonic decr, leftmost largest

    Time: O(n)
    Space: O(n)
*/

class Solution {
public:
    vector<int> maxSlidingWindow(vector<int>& nums, int k) {
        deque<int> dq;
        vector<int> result;
        
        int i = 0;
        int j = 0;
        
        while (j < nums.size()) {
            while (!dq.empty() && nums[dq.back()] < nums[j]) {
                dq.pop_back();
            }
            dq.push_back(j);
            
            if (i > dq.front()) {
                dq.pop_front();
            }
            
            if (j + 1 >= k) {
                result.push_back(nums[dq.front()]);
                i++;
            }
            j++;
        }
        
        return result;
    }
};

```

Bhai i would have not thought of pushing indexes on it bruhhhhh....

ya so basically you push index and wait till j+1>k after that you start incrementing the i counter also [ to make it a sliding window ] and this was its easier to remove elements that are not in the window by using

```cpp
if (i > dq.front()) {
   dq.pop_front();
   }
```

checks if the front index is less that the current back of the sliding window.

### BRIEF



### CONCLUSION