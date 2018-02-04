## 2018.2.4
* if与else if与switch区别

  多个if是所有if都进行判断按照最后一个满足条件的取值
  ```
  a=2;
  if(a==1) c=1;
  if(a==2) c=2;
  if(a%2==0) c=3;
  Output c=3
  ```
  if和else if是只要满足了条件就不对后面的else if进行判断
   ```
  a=2;
  if(a==1) c=1;
  else if(a==2) c=2;
  else if(a%2==0) c=3;
  Output c=2
  ```
  switch：
  
  ```
  switch(a)
  {
  case 1:
  case 2:
  case 3:
  break;
  }
  ```
  相当于if if
  
  ```
  switch(a)
  {
  case 1:
  break;
  case 2:
  break;
  case 3:
  break;
  }
  ```
  相当于else if
  
