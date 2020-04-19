# 第八周学习报告
* @Author 谢林枫
* @Date 20202.4.15
### 这周的学习报告没有去看其他的单片机内容，而是去学习c语言（老师讲课的内容），自己感觉现在跟不上老师的上课进度，有时候老师讲的都没听懂，所有我觉得我自己需要去课后复习。高数和离散数学准备期中考试了，估计自己是没有太多的时间花在课外技术的学习上，如果要是有时间分配出来我也是想去学51单片机而不是学32了，这是我目前的打算。

* [学习内容1](#1) | 
# <a id='1'>学习内容1</a>
# C语言学习（穷举法和递推法）
### 穷举法：在条件范围内对所有可能情况逐个验证；（循环或if实现）（本质是列举所有可能）
* 例子：求密码
```
  int main()
 {
   long m;
   for(m=67008;m<=67998;m+=10)
   {
     if(m%78==0&&m%67==0)
 	{
 	 printf("%ld",m);
	}
    }
    return 0;
 }
```
* 多穷举对象（百钱买百鸡）
```
#include<stdio.h>
void main()
{
	int x,y,z;
	for(x=0;x<=20;x++)
	{
		for(y=0;y<=33;y++)
		{
			for(z=0;z<=100;z++)
			{
				if((x+y+z==100)&&(5*x+3*y+z/3==100))
				printf("%6d%6d%6d\n",x,y,z); 
			}
		}
	}	
 } 
```
### 递推法：顺推法和逆推法；
* 走楼梯问题
```
#include<stdio.h>
void main()
{
	int fn,f1=1,f2=2,f3=4;   //f(n)=f(n-1)+f(n-2)+f(n-3)
	int n,i;
	scanf("%d",&n);          //初始条件f(1)=1,f(2)=2,f(3)=4 
	for(i=4;i<n;i++)
	{
		fn=f1+f2+f3;
		f1=f2;
		f2=f1;
		f3=fn;
	}
	printf("%d %d\n",n,fn);
}
```
## c语言实验报告例子(个人觉得比较难的)
* 输入N 个不大于100的正整数（Ν  ≤10 ）存入数组 a 中，输出 a 中的最大值，最小值及求出其平均值（保留两位小数），其中N的值由用户输入。

```
#include<stdio.h>
void main()
{
int i，N，a[100];
int max,min,sum;
float averge;
sum=0;
scanf("%d"，&N)；
for(i=0;i<N；i++)
{
 scanf("%d",&a[i]);
 sum=sum+a[i];
}
averge=(float)sum/N；
max=min=a[0];
if(a[i]>max)
max=a[i];
if(a[i]<min)
min=a[i];
printf("%d\t%d\t%.2f",max,min,averge);
}
```

* 餐饮服务质量调查打分(难点在于随机数的生成函数和)

```
       #include<time.h>
        srand((unsigned)time(NULL));
	a[N]=(rand()%10+11);
```

```
#include<stdio.h>
#include<stdlib.h>
void main()
{
 int score[40],count[12]=0;
 char str='*';
int i,j;
//printf("grade  count  histogram\n");
for(i=0;i<40;i++)
{
scanf("%d",&score[i]);
count[score[i]]++; 
}
for(j=1;j<=10;j++)
{
	printf("%d\t",j);
	printf("%d\t",count[j]);
	for(i=1;i<=count[j];i++)
	printf("%c",str);
	printf("\n");
	}
	return 0;
 } 
}
```

* 检验并打印魔方矩阵(我觉得难)
```
#include<stdio.h>
 int main()
 {
 	int a[5][5],i,j,sum,N;
	printf("输入一个5*5矩阵\n");
	for(i=0;i<5;i++) 
	{
		for(j=0;j<5;j++)
		{
			scanf("%d",&a[i][j]);
			if(a[i][j]>25||a[i][j]<1)//判断元素是不是在1-25之间 
			{
				printf("输入不正确\n");
				return 0;             //程序读到return 0,无论之后有多少语句都不执行 
			 } 
		}
	}
	N=5*(5*5+1)/2;                    //用N记录N(N^2+1)/2的值，
	                                  //每行每列及两条对角线上n个数和等于 N(N^2+1)/2
	for(i=0;i<5;i++)
	{
		sum=0;                        //每求一行 sum重新为0
		 for(j=0;j<5;j++)
  {
   sum=sum+a[i][j];
  }
  if(sum==N)                         //比较每一行之和是否等于N
   continue;                          //如果是跳过这次循环继续下一次循环
  else
  {
   printf("该矩阵不是魔方矩阵！\n");
   return 0;
  }
 }
 for(i=0;i<5;i++)
 {
  sum=0;                                  //每求一列sum重新置为0
  for(j=0;j<5;j++)
  {
   sum=sum+a[j][i];                            //比较每一列之和是否等于N
  }
  if(sum==N)
   continue;
  else
  {
   printf("该矩阵不是魔方矩阵！\n");
   return 0;
  }
 }
 sum=0;                                          //计算对角线求和前重置为0
 for(i=0;i<5;i++)
 {
  for(j=0;j<5;j++)
  {
   if(i==j)
    sum=sum+a[i][j];                             //计算从左到右对角线的和
  }
   
 }
 if(sum!=N)                                     //比较从左到右对角线的和之和是否等于N
 {
  printf("该矩阵不是魔方矩阵！\n");
  return 0;
  }
 sum=0;                                             //计算对角线求和前重置为0
 for(i=0;i<5;i++)                                   //计算从右到左对角线的和
 {
  j=4-i;
  sum=sum+a[i][j];
 }
 if(sum!=N)                                           //比较从右到左对角线的和是否等于N
 {
  printf("该矩阵不是魔方矩阵！\n");
  return 0;
  }
 else
  printf("该矩阵是魔方矩阵！\n");
  return 0;
}
```
* 函数的递归调用（计算年龄）
* 递归出口：age(n)=10,(n=1);递推方式：age(n)=age(n-1)+2,(n>1)
```
#include<stdio.h>
int main()
{
	int age(int n);
	printf("%d\n",age(5));
	return 0;
 } 
 
 int age(int n)
 {
 	int c;          //c用来存放函数的返回值的变量// 
 	if(n==1)        //如果n=1，年龄魏10 
 	   c=10;
 	else            
 	   c=age(n-1)+2;
 	return (c);
 }
```
* 递归方法求阶乘
```
#include<stdio.h>
int main()
{
	int fac(int n);
	int n;
	int y;
	printf("intput\n");
	scanf("%d",&n);
	y=fac(n);
	printf("%d的阶乘=%d\n",n,y);
	return 0;
}
int fac(int n)
{
	int f;
	if(n<0)
	printf("n<0数据错误");
	else
	if(n==0||n==1)
	f=1;
	else
	f=fac(n-1)*n;
	return (f);
}
```


