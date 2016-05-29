这是一个简单的猜拳游戏（剪子包子锤），让你与电脑对决。你出的拳头由你自己决定，电脑则随机出拳，最后判断胜负。

下面的代码会实现一个猜拳游戏，让你与电脑对决。你出的拳头由你自己决定，电脑则随机出拳，最后判断胜负。

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main()
{
    char gamer;  // 玩家出拳
    int computer;  // 电脑出拳
    int result;  // 比赛结果

    // 为了避免玩一次游戏就退出程序，可以将代码放在循环中
    while (1){
        printf("这是一个猜拳的小游戏，请输入你要出的拳头：\n");
        printf("A:剪刀\nB:石头\nC:布\nD:不玩了\n");
        scanf("%c%*c",&gamer);
        switch (gamer){
            case 65:  //A
            case 97:  //a
                gamer=4;
                break;
            case 66:  //B
            case 98:  //b
                gamer=7;
                break;
            case 67:  //C
            case 99:  //c
                gamer=10;
                break;
            case 68:  //D
            case 100:  //d
                return 0;
          
            default:
                printf("你的选择为 %c 选择错误,退出...\n",gamer);
                getchar();
                system("cls"); // 清屏
                return 0;
                break;
        }
      
        srand((unsigned)time(NULL));  // 随机数种子
        computer=rand()%3;  // 产生随机数并取余，得到电脑出拳
        result=(int)gamer+computer;  // gamer 为 char 类型，数学运算时要强制转换类型
        printf("电脑出了");
        switch (computer)
        {
            case 0:printf("剪刀\n");break; //4    1
            case 1:printf("石头\n");break; //7  2
            case 2:printf("布\n");break;   //10 3
        }
        printf("你出了");
        switch (gamer)
        {
            case 4:printf("剪刀\n");break;
            case 7:printf("石头\n");break;
            case 10:printf("布\n");break;
        }
        if (result==6||result==7||result==11) printf("你赢了!");
        else if (result==5||result==9||result==10) printf("电脑赢了!");
        else printf("平手");
        system("pause>nul&&cls");  // 暂停并清屏
    }
    return 0;
}





代码分析
1) 首先，我们需要定义3个变量来储存玩家出的拳头(gamer)、电脑出的拳头(computer)和最后的结果(result)，然后给出文字提示，让玩家出拳。

接下来接收玩家输入：

    scanf("%c%*c",&gamer);

注意：由于每次输入以回车结束，缓冲区中除了玩家输入的字母，还有回车符。回车符要跳过，以免影响下次输入。Scanf() 函数的格式控制字符串个数可以多于参数个数，scanf("%c%*c",&gamer);的作用是从缓冲区多输出一个字符（回车符），却不赋给任何变量。

玩家输入结束，使用 switch 语句判断输入内容，65(A)、97(a)、66(B)、98(b)、67(C)、99(c)、68(D)、100(d)为相应字符的ASCII码。

注意：system("cls"); 语句的作用是清屏。System() 函数用来执行 dos 命令，这里相当于在 dos 里输入 cls 命令。

2) 玩家出拳结束，电脑开始出拳。

电脑通过产生随机数来出拳：

    srand((unsigned)time(NULL));  //为了避免多次运行结果相同，故在前面加入上（需要time.h）
    computer=rand()%3;  //获取0~2的随机数

最后通过玩家和电脑出拳的和来判断输赢：

    result=(int)gamer+computer;
    // ...
    if (result==6||result==7||result==11) printf("你赢了!");
    else if (result==5||result==9||result==10) printf("电脑赢了!");
    else printf("平手");

这是一个很巧妙的算法，玩家和电脑出拳不同，result 的值就不同，且不会重复，见下表：

电脑 -- 玩家 	石头(4) 	剪刀(7) 	布(10)
石头(0) 	4 	7 	10
剪刀(1) 	5 	8 	11
布(2) 	6 	9 	12

3) 每次猜拳结束，暂停并清屏，进入下一次猜拳：

    system("pause>nul&&cls");   //暂停运行和清屏
