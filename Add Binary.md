## 问题分析：
#### 二进制数相加
补全较短二进制字符串然后对应相加
## 编程实现：
```C++
class Solution {
public:
    string addBinary(string a, string b) {
        string res;
        int na = a.size();
        int nb = b.size();
        int n = max(na, nb);
        bool carry = false;
        if (na > nb) {
            for (int i = 0; i < na - nb; ++i) b.insert(b.begin(), '0');
        }
        else if (na < nb) {
            for (int i = 0; i < nb - na; ++i) a.insert(a.begin(), '0');
        }
        for (int i = n - 1; i >= 0; --i) {
            int tmp = 0;
            if (carry) tmp = (a[i] - '0') + (b[i] - '0') + 1;
            else tmp = (a[i] - '0') + (b[i] - '0');
            if (tmp == 0) {
                res.insert(res.begin(), '0');
                carry = false;
            }
            else if (tmp == 1) {
                res.insert(res.begin(), '1');
                carry = false;
            }
            else if (tmp == 2) {
                res.insert(res.begin(), '0');
                carry = true;
            }
            else if (tmp == 3) {
                res.insert(res.begin(), '1');
                carry = true;
            }
        }
        if (carry) res.insert(res.begin(), '1');
        return res;
    }
};
```
## 总结体会：
* 二进制数相加并且保存在string中
  1. 如何将string和int之间互相转换
  2. 每位相加时可能进位会影响相加的结果。
  3. 两个输入string的长度可能不同,需新建一个string,长度是两条输入string中的较大,并把较短的输入string
     通过在开头加字符‘0’来与较大的长度对应,这时逐个从两个string的末尾取出字符,然后转为数字并相加,
     若大于等于2，则标记进位标志carry，并且给新string加入一个字符‘0’
* 将给定的二进制字符串转化为十进制相加再转化为二进制字符串
* 指针
> http://www.cnblogs.com/grandyang/p/4084971.html
