## 问题分析：
#### 爬梯子问题
梯子有n层,每次只能爬1或2步,爬到第n层的方法要么是从第n-1层一步上来的,要么是从n-2层2步上来的,
得递推公式:s[n]=s[n-1]+s[n-2]。 
## 编程实现：
```C++
class Solution {
public:
    int climbStairs(int n) {
        if (n<=1) return 1;
        vector<int> s(n);
        s[0]=1;
        s[1]=2;
        for (int i=2; i < n;i++) 
        {
         s[i]=s[i-1]+s[i-2];
        }
        return s.back();
    }
};
```
## 总结体会：
递归计算需要很多分支导致超时所以需要动态规划分配空间提高效率。
