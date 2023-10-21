# leetcode
/**My First program is for adding two numbers taking two integer values with singly liked list
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} l1
 * @param {ListNode} l2
 * @return {ListNode}
 */
var addTwoNumbers = function(l1, l2) {
    
    const iter = (n1,n2,rest = 0) => {
        //check iterations
        if (!n1 && !n2 && !rest)return null;
        //Adding two numbers
        const newVal = (n1?.val || 0) + (n2?.val || 0) + rest;
        const nextNode = iter(n1?.next,n2?.next, Math.floor(newVal/10));
        return new ListNode(newVal%10,nextNode);
    }
    return iter(l1,l2);
};
