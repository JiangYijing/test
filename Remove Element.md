## 问题分析：
#### 删除给定元素
本题要求在本数组中进行元素修改,因此要用变量标记数组修改位置,最终用新修改过的数组覆盖原数组。
## 编程实现
```C++
class Solution {
public:
    int removeElement(vector<int>& nums, int val) {
        int i=0,j=0;
        if(nums.empty()) return j;
        for(i=0;i<nums.size();i ++)
        {
            if(nums[i]!=val)
                nums[j++]=nums[i];//若该位不等于指定元素则该位等于原位;j,i都+1;进行下一位.
                                  //若该位等于指定元素则i+1;j保持原位不动直到在不是指定元素的位置将值赋给j位置.
        }
        return j;
        
    }
};
```
## 总结体会
1. vector(向量):C++中的一种数据结构(一个类),相当于一个动态数组,当无法确定需要数组的规模大小时,解决问题可达到最大节约空间的目的. 
   * **文件包含**：程序开头加上#include<vector>以包含所需要的类文件vector且需加using namespace std(std ::)。
   * **变量声明**：
              
              声明一个int向量以替代一维的数组:vector <int> a;(即声明了一个int数组a[],大小没有指定,可以动态的向里面添加删除)。
   
              用vector代替二维数组即需声明一个一维数组向量,而一个数组的名字其实代表的是它的首地址,
              
              所以就是声明一个地址的向量:vector <int *> a.
              
              同理想用向量代替三维数组也是一样,vector <int**>a;再往上面依此类推。
> http://blog.csdn.net/hancunai0017/article/details/7032383
2. 相当于数组中元素的替换,在同一数组内操作不能重新开辟一个数组
3. 用法：nums[j++],nums[++j]
4. 与上一题用快慢指针定位数组位置比较然后得出不同数字个数有相似之处但本题只需和给定元素进行比较而不需用两个指针来判断是否与数组中元素有重合。
