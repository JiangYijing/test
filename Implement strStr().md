## 问题分析
#### 字符串匹配
* 一个字符串中是否存在子串和给定的另外一个字符串相等;若存在则返回子串首位;不存在就返回-1。
* 实现strstr()（函数）. 返回needle(关键字)在haystack(字符串)中第一次出现的位置，如果needle不在haystack中，则返回-1
## 编程实现
```C++
class Solution {
public:
    int strStr(string haystack, string needle) {
        int i=0,j=1,num=0;
        if(needle.empty()) return 0;
        if(needle.size()>haystack.size()) return -1;
            for(i=0;i<haystack.size()-needle.size()+1;i ++)//[i<haystack.size()也可,但时间耗费大]优化(遍历到剩下的长度和子字符串相等的位置)
            {                                      //在与子字符串数相同剩下位置时若不等则一定不存在该子串;若相等则i不用再循环直接下面一位用i+j判断
                 if(needle[num]==haystack[i])
                {
                    for(j=1;j<needle.size();j ++)
                    {
                        if(needle[j]!=haystack[i+j])//由于第一位比较时i已经固定,所以比较下一位时i不能只+1,
                                                    //因为j是不断增加的(第num+1,num+2.....),所以i要随j的增加不断向下进位相对应的比较
                            break;
                    }
                    if(j==needle.size())//当循环到最后时(上一个循环结束输出是needle.size())加最后一个子串结束的判断
                    return i;//最后输出的是子串对应字符串首字母的位置,而并不是子串的元素总数
                             //这就是input"a","a";output 0;的原因
                }
            }
        return -1;//字符串没有与子串首元素相匹配
    }
};
```
## 总结体会
1. 暴力遍历字符串比较与子串的首元素,相同就进下一位的比较,直到将子串遍历完
2. 考虑空字符串和需判断字符串比总字符串长的情况
3. 细节问题+理解问题：遇到问题时返回去理解题意
> http://blog.csdn.net/jeffery1982/article/details/43916477
