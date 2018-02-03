## 问题分析：
求所有字符串的最长公共前缀，数组中所有字符串都有这个前缀
## 编码实现：
```class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
        int n=strs.size();
        string result;
        int pos=0,i=1;//position
        if(n==0) return result;
        for(pos=0;pos<strs[0].size();pos ++)
        {
            for(i=1;i<n;i ++)
            {
                if(strs[i].size()==pos||strs[i][pos]!=strs[0][pos])
                    return result;
            }  
            result.push_back(strs[0][pos]);
        } 
        return result;
    }
};
```
## 总结分析：
1. push_back函数用法：在vector类中作用为在vector尾部加入一个数据；string中的作用是字符串之后插入一个字符。
2. 两个循环，分层次进行比较，插入字符。
3. 注意字符串为0的情况需要判断。
