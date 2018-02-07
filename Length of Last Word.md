## 问题分析：
#### 求末尾单词长度
遍历字符串,如果遇到非空格的字符,判断其前面一个位置的字符是否为空格;
如果是的话,那么当前肯定是一个新词的开始,将计数器重置为1;
如果不是的话,说明正在统计一个词的长度,计数器自增1即可。
## 编程实现：
```C++
class Solution {
public:
    int lengthOfLastWord(string s) {
        int i=0,num=0;
        int j=s.size()-1;
        if(s.size()==0) return 0;
        for(i=0;i<s.size();i ++)
        {
            if(s[i]!=' ')
            {
                if(i!=0&&s[i-1]==' ')
                    num=1;
                else ++num;
            }
          }
        return num;
    }
};
```
## 总结体会：
* 当i=0的时候，无法访问前一个字符，所以这种情况要特别判断一下，归为计数器自增1那类。
* 结合字符和空格进行分析,不能分离的单纯考虑空格会出现的情况
> http://www.cnblogs.com/grandyang/p/4086298.html
