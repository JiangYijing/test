## 问题分析：
#### 数组融合排序
题给两个排序好的vactor数组,要求把数组2融合到数组1中,数组1的长度是足够的且融合后也按序。
## 编程实现：
```C++
class Solution {
  public:
      void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
          int i1=m-1,i2=n-1,k=m+n-1;
          while(i1>=0&&i2>=0)
          {
             if(nums1[i1]<nums2[i2])
              {
                  nums1[k--]=nums2[i2--];
             }
             else
             {
                 nums1[k--]=nums1[i1--];
             }
         }
         while(i2>=0)
         {
             nums1[k--]=nums2[i2--];
         }
         return;
     }
 };
 ```
## 总结体会：
要利用好nums1后n个空闲的空间
