## 问题分析
* 本题考查栈的用法，首先要找题目上大括号、中括号、小括号匹配的特点（主要是右半括号的特点要求）
* 首先遍历输入字符串，如果当前字符为左半边括号时，则将其压入栈中；
* 如果遇到右半边括号时，若此时栈为空，则直接返回false，如不为空，则取出栈顶元素；
* 栈顶元素若为对应的左半边括号，则继续循环，反之返回false。
## 编程实现
```class Solution {
public:
    bool isValid(string s) {
        stack<char> parentheses;
        int i=0;
        for(i=0;i<s.size();++ i)//(i ++)也可且减少运算时间
        {
            if(s[i]=='('||s[i]=='['||s[i]=='{')//字符串s[]判断左半括号字符，压入栈
                parentheses.push(s[i]);
            else 
            {
                if(parentheses.empty()) return false;
                if(s[i]==')'&&parentheses.top()!='(') return false;
                if(s[i]==']'&&parentheses.top()!='[') return false;
                if(s[i]=='}'&&parentheses.top()!='{') return false;
                parentheses.pop();//符合匹配条件输出
            }
        }
        return parentheses.empty();
    }
};
```
## 总结分析
1. 栈是限定仅在表尾进行插入和删除操作的线性表，数据暂时存储的地方。
   * 栈是允许在同一端进行插入和删除操作的特殊线性表。允许进行插入和删除操作的一端称为栈顶(top)，另一端为栈底(bottom)；
   * 栈底固定，而栈顶浮动；
   * 栈中元素个数为零时称为空栈。
   * 插入一般称为进栈（PUSH），删除则称为退栈（POP）。
   * 栈也称为后进先出表。
   * 栈可以用来在函数调用的时候存储断点，递归需用栈。
2. 定义一个栈的形式，栈顶的判断，压栈与栈的输出

