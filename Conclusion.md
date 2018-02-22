## 二叉树
二叉树的遍历是依次对树中每个结点均做一次且仅做一次访问
判断二叉树对称则比较左右的节点值

遍历方案：

前序
```C++
procedure first(i:longint);
begin
write(a[i]);
ifa[i*2]<>0then first(i*2）；
ifa[i*2+1]<>0then first(i*2+1）；
end;
```
中序
```C++
procedure mid(i:longint);
begin
if a[i*2]<>0 then mid(i*2）；
write(a[i]);
if a[i*2+1]<>0 then mid(i*2+1）；
end;
```
后序
```C++
procedure last(i:longint);
begin
if a[i*2]<>0 then last(i*2）；
if a[i*2+1]<>0 then last(i*2+1）；
write(a[i]);
end;
```

## 指针
* 利用各种函数关系可以简化问题
* 当出现循环超时的情况时,可以考虑在遍历中运用指针进行定位从而提高运算效率
* 指针数组：数组元素全为指针的数组；数组指针：指向数组首元素地址的指针
