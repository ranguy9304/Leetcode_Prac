TOPIC : [[SLIDING WINDOW]]
`2023-09-18

## TOPIC INFO 
Given the `head` of a linked list, remove the `nth` node from the end of the list and return its head.

**Example 1:**

![](https://assets.leetcode.com/uploads/2020/10/03/remove_ex1.jpg)

**Input:** head = [1,2,3,4,5], n = 2
**Output:** [1,2,3,5]

OK solution is simple two pointers fast and slow the slow one will start moving once the fast one moves by N+1 and then we just delete the element at the slow pointer->next.

```cpp
class Solution {

	public:
	
	ListNode* removeNthFromEnd(ListNode* head, int n) {
	
		ListNode* dummy = new ListNode(0);
		
		dummy->next = head;
		
		ListNode* fast = dummy;
		
		ListNode* slow = dummy;
		
	  
	
		// Move the fast pointer n+1 steps ahead
		
		for (int i = 0; i <= n; i++) {
		
			fast = fast->next;
		
		}
		
		  
		
		// Move both fast and slow pointers until fast reaches the end
		
		while (fast) {
		
			fast = fast->next;
			
			slow = slow->next;
		
		}
		
		  
		
		// Remove the nth node from the end
		
		ListNode* toRemove = slow->next;
		
		slow->next = slow->next->next;
		
		delete toRemove;
		
		  
		
		return dummy->next; // Return the modified list (skip dummy node)
	
	}

};
```




### BRIEF



### CONCLUSION