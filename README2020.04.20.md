# 第九周学习报告 
* @Author 谢林枫
* @Date 20202.4.20
### 这周的学习报告没能完成上周的学习计划，没有学习到单片机的内容。还有10天就要开学了，在家的学习效率真的很差，高数英语等什么科目都是一知半解，自己真的变懒了，莫得动力学习，自己落后了。哎，调整状态叭，我怕自己学不下去了（想哭.
* [学习内容1](#1) | [学习内容2](#2) | 

# <a id='1'>学习内容1</a>
### 局部变量和全局变量
#### 局部变量
* 定义：函数内部才能引用这些变量（同名变量互不干扰）
#### 全局变量
* 定义：源文件中的若干个函数外定义的变量称为外部变量(全局变量)

# <a id='2'>学习内容2</a>
* 阶乘和
```
#include<stdio.h>
int main()
{
	int fact(int n);
	int n,i,result=0;
	
	scanf("%d",&n);
	if(n<=0)
	printf("数据错误");
	for(i=1;i<=n;i++)
	{
		result=result+fact(i);
	}
	printf("1！+2！+...+n!=%d\n",result);
	return 0;
}
int fact(int n)
{
	int f;
	if(n==0||n==1)
	f=1;
	else
	f=fact(n-1)*n;
	return (f);
}
```
* 水仙花数
```
#include<stdio.h>
#define fun(x) x*x*x

void main()
{
	int i,num1=0,num2=0,num3=0,sum;
	printf("'water flower'number is:\n");
	for(i=0;i<1000;i++)
	{
		num1=i/100;
		num2=i%100/10;
		num3=i%10;
		sum=fun(num1)+fum(num2)+fun(num3);
	}
	if(sum==i)
    printf("%d"sum);	
}
```
* 出加法题
````
#include<stdio.h>
#include<stdio.h>
#include<time.h>
void main()
{
	int i,a,b,c,sum,score=0,error=0;
	for(i=1;i<11;i++)
	{
		srand((unsigned)time(NULL));
	    a=rand()%10+1;
	    b=rand()%10+1;
	    sum=a+b;
	    printf("%d+%d=",a,b);
		scanf("%d",&c);
		if(sum==c)
		{
			score=score+10;
			printf("Right!\n");
		}
		else
		{
			printf("Not correct!\n");
			error++;
		}  
 } 
        printf("分数:%d\t错误题数：%d\n",score,error);
}
```
* 函数调用求平均分
```
#include<stdio.h>
#include<stdlib.h> 
#define MAXNUM 40
float averscore(float score[],int N);
void inputscore(float score[],int N);
int main()
{
	int N;
	float score[MAXNUM],avg;
	//printf("输入num：\n");
	scanf("%d",&N);
	if(N<2||N>40)
	{
		printf("输入错误");
		exit(0);
	}
	inputscore(score,N);
	avg=averscore(score,N);
	printf("平均分是：%.2f",avg);
	//printf("1900300506谢林枫"); 
	return 0; 
}

float  averscore(float score[],int N)
{
	int i;
	float sum=0.00;
	float aver=0.00;
	for(i=0;i<N;i++)
	{
		sum=sum+score[i];
	 } 
	aver=sum/N;
	 return aver;
 } 

void inputscore(float score[],int N)
{
	int i;
	//printf("输入成绩：\n");
	for(i=0;i<N;i++)
	{
		scanf("%f",&score[i]);
		if(score[i]<0||score[i]>100)
		{
			printf("请重新输入\n");
			i=i-1;
		 } 
	}
}
```
