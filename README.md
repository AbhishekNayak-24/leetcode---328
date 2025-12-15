# leetcode---328
oddevenlinkedlist
//code in c++
class Solution {
 public:
  ListNode* oddEvenList(ListNode* head) {
    ListNode oddHead(0);
    ListNode evenHead(0);
    ListNode* odd = &oddHead;
    ListNode* even = &evenHead;

    for (int isOdd = 0; head; head = head->next)
      if (isOdd ^= 1) {
        odd->next = head;
        odd = odd->next;
      } else {
        even->next = head;
        even = even->next;
      }

    odd->next = evenHead.next;
    even->next = nullptr;
    return oddHead.next;
  }
};

Was this page helpful?


 Back to top
Discover more
Python
Previous
327. Count of Range Sum
Next
329. Longest Increasing Path in a Matrix
Copyright © 2019 - 2025 P.-Y. Chen
Made with Material for MkDocs
