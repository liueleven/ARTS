# ARTS-week-08-eleven

### 1. Algorithm
> 编程训练和学习
##### 描述
```
请判断一个链表是否为回文链表。

示例 1:

输入: 1->2
输出: false
示例 2:

输入: 1->2->2->1
输出: true
```
##### 思路一
使用快慢指针思路找到中间点，快指针是慢指针的2倍，当快指针到最后一个元素时，慢指针
刚好到中间点，当然还要考虑下元素的奇偶性，使用栈来存储元素节点，出栈就相当把元素反转了
```
public class Plalindrome {


    public static void main(String[] args) {
        // 偶数
//        ListNode node5 = new ListNode(0,null);
//        ListNode node4 = new ListNode(1,node5);
//        ListNode node3 = new ListNode(3,node4);
//        ListNode node2 = new ListNode(3,node3);
//        ListNode node1 = new ListNode(1,node2);
//        ListNode root = new ListNode(0,node1);
        // 奇数
        ListNode node4 = new ListNode(1,null);
        ListNode node3 = new ListNode(3,node4);
        ListNode node2 = new ListNode(-2,node3);
        ListNode node1 = new ListNode(3,node2);
        ListNode root = new ListNode(1,node1);
        Plalindrome p = new Plalindrome();
        boolean result = p.isPalindrome(root);
        System.out.println(result);
    }

    public boolean isPalindrome(ListNode root) {

        if(root == null) {
            return true;
        }

        // 使用快慢指针
        ListNode fast = root;
        ListNode slow = root;
        // 使用栈先进后出的特点，相当于反转链表了
        Stack<ListNode> stack = new Stack();
        while (fast != null && fast.next != null) {
           stack.push(slow);
           fast = fast.next.next;
           slow = slow.next;
        }

        // 如果是奇数
        if (fast != null) {
            slow = slow.next;
        }

        while (!stack.isEmpty()) {
            if(stack.pop().val != slow.val) {
                return false;
            }
            slow = slow.next;
        }
        return true;

    }




    static class ListNode {
        int val;
        ListNode next;

        public ListNode(int val, ListNode next) {
            this.val = val;
            this.next = next;
        }

        public ListNode() {
        }

        public int getVal() {
            return val;
        }

        public void setVal(int val) {
            this.val = val;
        }

        public ListNode getNext() {
            return next;
        }

        public void setNext(ListNode next) {
            this.next = next;
        }
    }

}

```







### 2. Review
> 英文学习
看了SpringBoot官方文档33-34章节
### 3. Tip
> 工作知识点、技巧

最近看到SpringBoot官方文档中的附录有很多application.properties[常用的属性配置](https://docs.spring.io/spring-boot/docs/2.1.3.RELEASE/reference/htmlsingle/#common-application-properties)

参考[网站](http://www.opsschool.org/text_editing_101.html#vi-basics)
### 4. Share
> 思考、总结、感悟
前段时间的996ICU事件，当时觉得非常可笑，这明明是个市场供需问题。但是最近看薛兆丰的经济学中讲到权利，其实很多习以为常的基本权利，本来就没有，都是靠人一点点，花几百年的时间争取来的
。种族，性别，等级制度、教育等等。这样想想，向第一个发声的大佬致敬

