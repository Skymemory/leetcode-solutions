## 45. Jump Game II

题意：给一个非负数组，起初在第一个位置，位置的值代表每次可以向后跳的最大长度。
问最少跳跃多少次可以到达最后一个位置。  

思路：

### 方法1：暴力 BFS


从第一个位置开始，将能够调到的位置放入队列（已存在则忽略），并记录对应的调数。
遇到最后位置时就找到答案。  
复杂度：O(n^2)
结果：超时

### 方法2：暴力DP


递归求出一个位置能跳到的新位置到最后位置的最小值，当前位置的加一。 
复杂度：O(n^2)
注：可以倒着循环，就不会爆栈
结果：超时

### 方法3：DP + 区间最优值（线段树/树状数组等数据结构）


暴力DP的时候，假设当前位置是 P，能够跳的长度是 L， 我们的目标是找到 [P+1, P+L] 区间内每个位置到最后一个位置的最小条数。
由于倒着计算时，区间内每个位置的最小条数已经计算出来了，使用线段树维护，则可以 log(n) 找到区间内最小值。  
复杂度：O(n log(n))
结果：通过

### 方法4：贪心  


以输入数据为例，[2,3,1,1,4]
对于第一位置数字 2， 可以跳到 第二个位置和第三个位置，跳数分别是 1
那么对于第二个位置 3， 可以直接从第四个位置开始计算，而没必要重复计算第三个位置的最优条数（贪心的地方）
原理1：BFS 最先遇到的肯定是最优的。
原理2：如果一个位置可以在 K 跳到达，则这个位置之前的位置，都可以在 K 条之内到达。

证明：假设B 位置的最优跳数是K，且从A位置跳过来, 则 [A+1, B]区间的位置都可以从 A 跳过来，所以最优条数都不会大于 K。  而A 位置的条数肯定是 K-1, 之前的同理即可证明。

根据上面说的贪心的方法，就可以在O(n)内找到答案了
复杂度：O(n)
结果：通过


## C++ 语言


[tiankonguse.cpp](./tiankonguse.cpp)


