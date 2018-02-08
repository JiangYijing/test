## 问题分析:
#### 数字加一
分个位数的不同情况讨论。
## 编程实现:
```C++
class Solution {
public:
    vector<int> plusOne(vector<int>& digits) {
        int i=digits.size()-1;
        for(i=digits.size()-1;i>=0;i --)
        {
            if(digits[i]==9)
                digits[i]=0;
            else 
            {
                digits[i]+=1;
                return digits;
            }   
        }
        if(digits.front()==0) digits.insert(digits.begin(),1);//front是指第一位;begin指的是最前面(第一位的前面)
        return digits;
        
    }
};
## 总结体会
1. 尾位为9要加一进位,然后该位变为0。
2. 若是第一位是9,则应该再加一位所以要查运算完的第一位是否为0，若是则在最前头加一个1。
