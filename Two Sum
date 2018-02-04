问题分析：此题主要考查是指针的简单用法，结合数组实现。本题的化简之处为只输出一种结果且每个数字只用一次
编程实现：
/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
int* twoSum(int* nums, int numsSize, int target)
{
    int* n=malloc(sizeof(int)*2);
    int i=0,j=0;
    for(i=0;i<numsSize-1;i++)
    {
        for(j=i+1;j<numsSize;j++)
        {
            if(nums[i]+nums[j]==target)
            {
                n[0]=i;
                n[1]=j;
            }
        }
    }
   return n; 
}
总结体会：由于利用向系统申请分配指定size个字节的内存空间的mallo函数的返回值是void *类型，所以使用（int *）将返回值强制转换成指向int类型的指针
         若不用指针会出现“load of null pointer of type 'const int'”结果，提醒指向空指针，且利用指针可以简化程序。


