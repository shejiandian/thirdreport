实验三 分支结构程序设计 
一、实验目的 
1、了解C语言表示逻辑量的方法（以0代表“假”，以1代表“真”）。 
2、学会正确使用逻辑运算符和逻辑表达式。 
3、熟练掌握if语句和switch语句。 
4、熟悉分支结构程序设计。 
二、实验准备 
1、复习关系、逻辑、条件运算符和表达式。 
2、复习if语句的三种形式。 
3、复习if语句的嵌套并能正确分析。 
4、复习多分支选择switch语句。 
三、实验内容 
1、调试下列程序 
#include <stdio.h> 
void main() 
{ 
int a,b,max,min; 
scanf("%d%d",&a,&b); 
if (a>b) {max=a;min=b;} 
else {min=a;max=b;} 
printf("max=%d,min=%d\n",max,min); 
} 
![image](https://github.com/user-attachments/assets/57d71f0b-ff85-41bf-983d-6e96e84da08c)

问题： 
•此程序的功能是什么？  比较数字大小并输出
•请用条件表达式语句（？：）修改程序使之完成相同的功能。 
#include <stdio.h>
int main()
{
    int a,b;
    int max,min;
    scanf("%d %d",&a,&b);
    max = min = a;
    max = max > b ? max : b;
    min = min < b ? min : b;
    printf("max=%d,min=%d\n",max,min);
    return 0;
}
2、编程 
（a）有一函数 
用scanf 函数输入x的值（分别为x<1、1≤x<10、x≥10三种情况），求y值。 
#include <stdio.h>
int main()
{
    int x,y;
    scanf("%d",&x);
    if(x < 1){
        y = x;
    }
    else if(x >= 1 && x < 10){
        y = 2 * x - 1;
    }
    else if(x >= 10){
        y = 3 * x - 11;
    }
    printf("y=%d\n",y);
    return 0;
}
![image](https://github.com/user-attachments/assets/7d376eae-c8ca-46e1-a1c2-2646abe97412)

（b）给出一个百分制成绩，要求输出成绩等级‘A’‘ B’‘ C’‘ D’‘ E’。 
（90 分以上为‘A’， 81~89 分为‘B’， 70~79 分为‘C’， 60~69 分为‘D’， 60 分以下为
‘E’。） 
#include <stdio.h>
int main()
{
    int score;
    scanf("%d",&score);
    switch(score / 10){
        case 10:
        case 9:printf("等级为:A\n");break;
        case 8:printf("等级为:B\n");break;
        case 7:printf("等级为:C\n");break;
        case 6:printf("等级为:D\n");break;
        default:printf("等级为:E\n");break;
    }
    return 0;
}
![image](https://github.com/user-attachments/assets/ce9b244e-0968-454d-8c50-ad180352cedf)

（c）有一个不多于5位的正整数，要求： 
•求出它是几位数。 
•分别打印出每一位数字。 
•按逆序打印出各位数字，例如原数为321，应输出123。
#include <stdio.h>
int main()
{
    int cnt,a;
    scanf("%d",&a);
    int b = a;
    int c = a;
    while(a > 0){
        a /= 10;
        cnt ++;
    }
    printf("该数是%d位数\n",cnt);
    
    for(int i = cnt - 1;i >= 0;i --){
        int divisor = 1;
        for(int j = 0;j < i;j ++){
            divisor *= 10;
        }
        int digit = (c / divisor) % 10;
        printf("%d ",digit);
    }
    printf("\n");
    
    while(b != 0){
        int dight = b % 10;
        printf("%d",dight);
        b /= 10;
    }
    return 0;
}
![image](https://github.com/user-attachments/assets/5a653650-1d23-43df-8811-29ab6e7856bc)
