## My Problem Solving 

### Day 1 (19/07/2024):

#### 1) Rotate Array

---
``` java 
    class Solution {
    public void rotate(int[] nums, int k) {
        int n = nums.length;
        if(k>n){
            k%=n; //if k is grather than size of arr
        }
        arrRotate(nums,0,n-1);
        arrRotate(nums,0,k-1);
        arrRotate(nums,k,n-1);
        System.out.print(nums);
    }
    public void arrRotate(int n[], int s,int e){
        while(s<=e){
            int t = n[s];
            n[s] = n[e];
            n[e] = t;
            s++;
            e--;
        }
    }
}
//CODED BY SANJAYSUDHAN S
```

[![YouTube video player](https://img.youtube.com/vi/TYT5TJSfGlo/0.jpg)](https://www.youtube.com/watch?v=TYT5TJSfGlo)

### [LeetCode Problem Link](https://leetcode.com/problems/rotate-array)

---
### Day 2 (20/07/2024):

#### 2) Matrix Diagonal Sum
```java
class Solution {
    public int diagonalSum(int[][] mat) {
        int sum = 0;
        for(int i =0;i<mat.length;i++){
            for(int j = 0;j<mat[i].length;j++){
                if(i == j)
                 sum +=mat[i][j]; 
                if ((i+j) == mat.length-1 && i!=j)
                 sum+=mat[i][j];
            }
        }
        return sum;
    }
}
// CODED BY SANJAYSUDHAN S
```
### [LeetCode Problem Link](https://leetcode.com/problems/matrix-diagonal-sum)
---
### Day 3 (21/07/2024):

#### 3) Minimum Moves to Equal Array Elements
```java
class Solution {
    public int minMoves(int[] nums) {
        int min = nums[0];
        for(int i =1;i<nums.length;i++){
            if(nums[i]<min){
                min = nums[i];
            }
        }
        int moves = 0;
        for (int i = 0; i < nums.length; i++) {
            moves += nums[i] - min;
        }
        
        return moves;
    }
}
// CODED BY SANJAYSUDHAN S
```
### [LeetCode Problem Link](https://leetcode.com/problems/minimum-moves-to-equal-array-elements/description/)
---
### Day 4  (05/08/2024):

#### 4) Middle of the Linked List
```java
class Solution {
    public ListNode middleNode(ListNode head) {
        ListNode t1 = head;
        int c = 0;
        while(t1!=null){
            c++;
            t1=t1.next;
        }
        c/=2;
        for(int i =0;i<c;i++){
            head = head.next;
        }
        return head;
    }
}
```
### [LeetCode Problem Link](https://leetcode.com/problems/middle-of-the-linked-list/description/)
---
### Day 5  (13/08/2024):

#### 5) Reverse a linked list
```java
class Solution {
    // Function to reverse a linked list.
    Node reverseList(Node head) {
        // code here
        Node prev = null;
        Node next = null;
        Node curr = head;
        while(curr!=null){
            next = curr.next;
            curr.next = prev;
            prev = curr;
            curr = next;
        }
        head = prev;
        return head;
    }
}
```
### [GFG Problem Link](https://www.geeksforgeeks.org/problems/reverse-a-linked-list/1?page=1&category=Linked%20List&sortBy=submissions)
### [LeetCode Problem Link](https://leetcode.com/problems/reverse-linked-list/)

---
### Day 6  (14/08/2024):

#### 6) Reverse a linked list
```java
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        if(head == null) 
            return head;
        ListNode temp = head;
        while(temp.next!=null){
            if(temp.val==temp.next.val){
                temp.next = temp.next.next;
            }
            else{
            temp = temp.next;
            }
        }
        return head;
    }
}
```
### [GFG Problem Link](https://www.geeksforgeeks.org/problems/reverse-a-linked-list/1?page=1&category=Linked%20List&sortBy=submissions)
### [LeetCode Problem Link](https://leetcode.com/problems/remove-duplicates-from-sorted-list/)

---
### Day 7  (15/08/2024):

#### 7) Odd Even Linked List
```java
class Solution {
    public ListNode oddEvenList(ListNode head) {
        if(head == null) return null;
        if(head.next == null) return head;

        ListNode oddHead = new ListNode(0);
        ListNode evenHead = new ListNode(0); 
        ListNode odd = oddHead;
        ListNode even = evenHead;

        ListNode current = head;

        int i = 1;
        while(current != null){
            if(i % 2 == 0) {
                even.next = current;
                even = even.next;
            } else {
                odd.next = current;
                odd = odd.next;
            }
            current = current.next;
            i++;
        }

        even.next = null;
        odd.next = evenHead.next;

        return oddHead.next;
    }
}
```
### [LeetCode Problem Link](https://leetcode.com/problems/odd-even-linked-list/description/)

---
