876. Middle of the Linked List

题意：输出链表的中位数。
如果有两个，输出后面那个。  


题意：最简单的就是先循环一遍，求出链表的长度。  
然后计算出答案在第几个，然后循环找到对应的链表节点。  


另一种比较优雅的方法是快慢指针，但是需要对边界特殊处理。  

## C++语言  

[tiankonguse.cpp](./tiankonguse.cpp)

