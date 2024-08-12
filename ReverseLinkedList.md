# Reversing a Linked List


### Java Code

```java

class Solution {
    public ListNode reverseList(ListNode head) {
        ListNode prev = null;  
        ListNode current = head;  

        while (current != null) {
            ListNode nextNode = current.next;  
            current.next = prev;  
            prev = current;  
            current = nextNode;  
        }

        return prev;  
    }
}

```
![image](https://github.com/user-attachments/assets/0cecbeea-bf1c-4ce9-9b06-c7e26d3dc949)
