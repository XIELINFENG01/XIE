# <a id='1'>学习内容1</a>
# 第14周学习报告  
* @Author 谢林枫
* @Date 20202.5.28
* [学习内容1](#1) | [学习内容2](#2) | 
## 这周学习内容为1.c语言（牛客网）写题目；2.STM32的学习，学的不多；3.英语四级准备；4.离散数学写题复习；学长学姐说之后会很忙，叫我们现在就要着手去做，但是我不知道现在要开始准备什么，希望学姐学长能大概指一下方向。

# <a id='1'>学习内容1</a>
## c语言学习
* 1.int a=sizeof(int / long / short / long long );(sizeof()是保留字，它的作用是求某类型或某变量类型的字节数)
* 2.要输出“某字符串 ”则要加 “\”转义；例如：printf（“printf(\"hello world!\\n\");\n”）;
* 3.printf("0%o,0x%X",1234,1234)  (八进制——%d)
* 4.printf("%#o %#X", 1234, 1234);
* //#号，标识符type是o、x、X时，增加前缀0、0x、0X；
* 5.printf("%15d",0xABCDEF)（16进制之前要加0x）(10进制所占域宽为15，%md输出域宽为m的十进制整数)；
* 6.本题对printf函数的原型进行了解，平常编程中可以对printf函数的返回值进行检查，以防输出错误。(我做了正确的但是就是不给我通过，多交了几遍就过了这啥啊这是)

```
#include <stdio.h>
int main()
{ int len = printf("Hello world!"); printf("\n");
printf("%d", len);
return 0; 
}
```

* 7.学生成绩的输入输出；
* 8.（1）getchar()调用字符输入函数；


```
    （2）#include<stdio.h>
    int main()
    {
        char a;
        scanf("%c".a);
        for(int i=0;i<5;i++)
        {
            for(int j=5-i;j>0;j--)
            {
                printf(" ");
            }
        }
        for(int m=1;m<=i;m++)
        {
            printf("%c",a);
        }
            printf("\n");
        return 0;
    }
```


* 9.（1）通过scanf函数的%m格式控制可以指定输入域宽，输入数据域宽（列数），按此宽度截取所需数据；
*（2）str的用法

```
#include<stdio.h>
int main()
{
    char str[10];
    scanf("%s",str);
    printf("year=%c%c%c%c\n",str[0],str[1],str[2],str[3]);
    printf("month=%c%c\n",str[4],str[5]);
    printf("date=%c%c\n",str[6],str[7]);
    return0;
} 
```

* (3） printf("year=%04d\nmonth=%02d\ndate=%02d", a/10000, a%10000/100, a%100);
* 10.字符串及数字的反向输出
* (1)数字反向输出；

```
#include <stdio.h>
int main()
{
    int n;
    scanf("%d",&n);
    int a=n/1000;
    int b=(n/100)%10;
    int c=(n/10)%10;
    int d=n%10;
    printf("%d%d%d%d\n",d,c,b,a);
}
```

* (2）字符串的反向输出
* 字符数组与字符串关系

```
char str1[]={‘h’,’e’,’l’,’l’,’o’,’ ‘,’w’,’o’,’r’,’l’,’d’};
char str2[]=”hello world”;
```

* 上面的语句定义了 2 个字符数组，其中 str1[]在初始化后，最后一个元素不是’\0’，而 str2[]
* 在初始化后，最后一个字符是’\0’，因此 str1[]不能当做字符串来处理，而 str2[]是可以当做
* 字符串来处理的，因为它最后一个字符是’\0’。
* [原文连接]（https://blog.csdn.net/qq_39368007/article/details/82381673）
```
#include<stdio.h>
#include<string.h>
int main()
{
  char str[]="abcdef";
  int i,j,k;
j=strlen(str)-1;
for(i=0;i<j;i++,j--)
{
 k=str[i];
 str[i]=str[j];
 str[j]=k;
}
printf("%s",str);
return 0;
}
```

* 11.精度float不够，double更长，定义r为double型scanf会出现错误改为%lf;
* 分数存在时整形换成浮点型，（4.0/3.0）；
* 12.字母大小写的变换
* (1)

```
char ch;
    while((scanf("%c",&ch))!=EOF)//ch=getchar()!=EOF;
    {
        if(ch>='A' && ch<='Z')
          ch+=32;
        putchar(ch);
    }
```

* （2）
```
int diff = 0X61 - 0X41;  
    char ch;
    while(scanf("%c\n",&ch)!=EOF){
        printf("%c\n",ch+diff);
 ```
* 13.2的n次方左移实现

* (1）

```
#include<math.h>
int main()
{
 int  num;
while(scanf("%d",&num)!=EOF)
{
  printf("%d",(int)pow(2,num));//pow运算之后的数据类型是double型，要强制转换为int
}
}
```

* (2）启示左移一位就可以变为2的次方

```
while((scanf("%d",&a)!=EOF))
{
printf("%d\n",1<<a);
}
```

## 32学习
* 程序下载方法1：
* 1.硬件连接——usb连接（PA9,PA10串口1引脚，必须连接usb串口的发送接收电路，usb线必须连接usb-232下载口，跳线帽B0,B1要接地）
——isp下载，只能使用串口1，对应串口发送接收引脚PA9,PA10，不能使用其他串口；
* 2.环境准备：CH340驱动安装；
* 3.


