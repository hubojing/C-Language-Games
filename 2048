#include<stdio.h>
#include<conio.h>   //使用getch()函数 
#include<time.h> 
#include <stdlib.h>
int num[4][4];
int score, gameover, ifappear, gamew, gamef,move;
char key;
void explation()
{
    void menu();
    system("cls");
    printf("\t\t*****************************************\t\t\n");
    printf("\t\t*****************************************\n");
    printf("\t\t******************游戏规则***************\n");
    printf("\t\t*****************************************\n");
    printf("\t\t*****************************************\t\t\n");
    printf("玩家可以选择上、下、左、右或W、A、S、D去移动滑块\n");
    printf("玩家选择的方向上若有相同的数字则合并\n");
    printf("合并所得的所有新生成数字相加即为该步的有效得分\n");
    printf("玩家选择的方向行或列前方有空格则出现位移\n");
    printf("每移动一步，空位随机出现一个2或4\n");
    printf("棋盘被数字填满，无法进行有效移动，判负，游戏结束\n");
    printf("棋盘上出现2048，获胜，游戏结束\n");
    printf("按上下左右去移动滑块\n");
    printf("请按任意键返回主菜单...\n");
    getch();
    system("cls");
    main();
}
void gamefaile()
{
    int i, j;
    system("cls");
    printf("\t\t*****************************************\t\t\n");
    printf("\t\t*****************************************\n");
    printf("\t\t******************you fail***************\n");
    printf("\t\t*****************************************\n");
    printf("\t\t*****************************************\t\t\n");
    printf("\t\t\t---------------------\n\t\t\t");
    for (j = 0; j<4; j++)
    {
        for (i = 0; i<4; i++)
            if (num[j][i] == 0)
                printf("|    ");
            else
                printf("|%4d", num[j][i]);
        printf("|\n");
        printf("\t\t\t---------------------\n\t\t\t");
    }
    printf("你的成绩：%d,移动了%d步\n", score,move);
    printf("请按任意键返回主菜单...\n");
    getch();
    system("cls");
    main();
 
}
void gamewin()
{
    int i, j;
    system("cls");
    printf("\t\t*****************************************\t\t\n");
    printf("\t\t*****************************************\n");
    printf("\t\t*******************you win***************\n");
    printf("\t\t*****************************************\n");
    printf("\t\t*****************************************\t\t\n");
    printf("\t\t\t---------------------\n\t\t\t");
    for (j = 0; j<4; j++)
    {
        for (i = 0; i<4; i++)
            if (num[j][i] == 0)
                printf("|    ");
            else
                printf("|%4d", num[j][i]);
        printf("|\n");
        printf("\t\t\t---------------------\n\t\t\t");
    }
    printf("你的成绩：%d,移动了%d步\n", score,move);
    printf("请按任意键返回主菜单...\n");
    getch();
    system("cls");
    main();
}
void prin()
{
    int i, j;
    system("cls");
    printf("\t\t*****************************************\t\t\n");//输出界面
    printf("\t\t*****************************************\n");
    printf("\t\t******************游戏开始***************\n");
    printf("\t\t*****************************************\n");
    printf("\t\t*****************************************\t\t\n");
    printf("\t\t      请按方向键或W、A、S、D移动滑块\n");//输出操作提示语句
    printf("\t\t          按ESC返回至主菜单\n");
    printf("\t\t\t---------------------\n\t\t\t");
    for (j = 0; j<4; j++)                 //输出4*4的表格
    {
        for (i = 0; i<4; i++)
            if (num[j][i] == 0)
                printf("|    ");
            else
                printf("|%4d", num[j][i]);
        printf("|\n");
        printf("\t\t\t---------------------\n\t\t\t");
    }
    printf("你的成绩：%d，移动了%d步\n", score,move);//输出得分和移动步数
}
void appear()
{
    int i, j,ran,t[16],x=0,a,b;
    srand((int)time(0));          //随机种子初始化
    for (j = 0; j < 4; j++)      //将空白的区域的坐标保存到中间数组t中
        for (i = 0; i < 4;i++)
            if (num[j][i] == 0)
            {
                t[x] = j * 10 + i;
                x++;
            }
    if (x == 1)            //在t中随机取一个坐标
        ran = x - 1;
    else
        ran = rand() % (x - 1);
    a = t[ran] / 10;      //取出这个数值的十位数
    b = t[ran] % 10;     //取出这个数值的个位数
    srand((int)time(0));
    if ((rand() % 9)>2)    //在此空白区域随机赋值2或4
        num[a][b] = 2;
    else
        num[a][b] = 4;
}
void close()
{
    exit(0);
}
void add(int *p)
{
     
    int i=0, b;
    while (i<3)
    {
        if (*(p + i) != 0)
        {
            for (b = i + 1; b < 4; b++)
            {
                if (*(p + b) != 0)
                    if (*(p + i) == *(p + b))
                    {
                    score = score + (*(p + i)) + (*(p + b));
                    *(p + i) = *(p + i) + *(p + b);
                    if (*(p + i) == 2048)
                        gamew = 1;
                    *(p + b) = 0;
                    i = b + i;
                    ++ifappear;
                    break;
                    }
                    else
                    {
                        i = b;
                        break;
                    }
            }
            if (b == 4)
                i++;
        }
        else
            i++;
    }
 
}
void Gameplay()
{
    int i, j, g, e, a, b[4];
    appear();
    appear();
    while (1)
    {
        if (ifappear!=0)
            appear();
        prin();
        key = getch();
        switch (key)
        {
        case 'w':
        case 'W':
        case 72:
            ifappear = 0;
            for (j = 0; j < 4; j++)
            {
                for (i = 0; i < 4; i++)
                {
                    b[i] = num[i][j];
                    num[i][j] = 0;
                }
                add(b);
                e = 0;
                for (g = 0; g < 4; g++)
                {
                    if (b[g] != 0)
                    {
                        num[e][j] = b[g];
                        if (g != e)
                            ++ifappear;
                        e++;
                    }
                }
            }
            if (ifappear!=0)
                ++move;
        break;
        case 's':
        case 'S':
        case 80:
            ifappear = 0;
            for (j = 0; j < 4; j++)
            {
                for (i = 0; i < 4; i++)
                {
                    b[i] = num[i][j];
                    num[i][j] = 0;
                }
                add(b);
                e = 3;
                for (g = 3; g>=0; g--)
                {
                    if (b[g] != 0)
                    {
                        num[e][j] = b[g];
                        if (g != e)
                            ++ifappear;
                        e--;
                    }
                }
            }
            if (ifappear != 0)
                ++move;
        break;
        case 'a':
        case 'A':
        case  75:
            ifappear = 0;
            for (j = 0; j < 4; j++)
            {
                for (i = 0; i < 4; i++)
                {
                    b[i] = num[j][i];
                    num[j][i] = 0;
                }
                add(b);
                e = 0;
                for (g = 0; g < 4; g++)
                {
                    if (b[g] != 0)
                    {
                        num[j][e] = b[g];
                        if (g!=e)
                            ++ifappear;
                        e++;
                    }
                }
            }
            if (ifappear != 0)
                ++move;
        break;
        case 'd':
        case 'D':
        case  77:
            ifappear = 0;
            for (j = 0; j < 4; j++)
            {
                for (i = 0; i < 4; i++)
                {
                    b[i] = num[j][i];
                    num[j][i] = 0;
                }
                add(b);
                e = 3;
                for (g = 3; g >=0; g--)
                {
                    if (b[g] != 0)
                    {
                        num[j][e] = b[g];
                        if (g!=e)
                            ++ifappear;
                        e--;
                    }
                }
            }
            if (ifappear != 0)
                ++move;
        break;
        case 27:
            system("cls");
            main();
            break;
 
        }
        for (j = 0; j < 4; j++)
        {
            for (i = 0; i < 4; i++)
            {
                if (j < 3)
                {
                    if (i < 3)
                    {
                        if (num[j][i] == num[j + 1][i] || num[j][i] == num[j][i + 1] || num[j][i] == 0)
                        {
                            gamef = 0;
                            break;
                        }
                        else
                            gamef = 1;
                    }
                    else
                    {
                        if (num[j][i] == num[j + 1][i] || num[j][i] == 0)
                        {
                            gamef = 0;
                            break;
                        }
                        else
                            gamef = 1;
                    }
                }
                else
                {
                    if (i < 3)
                    {
                        if (num[j][i] == num[j][i + 1] || num[j][i] == 0 || num[j][i + 1] == 0)
                        {
                            gamef = 0;
                            break;
                        }
                        else
                            gamef = 1;
                    }
                }
 
            }
            if (gamef == 0)
                break;
        }
        if (gamef == 1 || gamew == 1)
            break;
 
    }
    if (gamef == 1)
        gamefaile();
    else
        gamewin();
}
void menu()
{
    int n;
    printf("\t\t*****************************************\t\t\n");            //输出游戏菜单的图形
    printf("\t\t*              1、开始游戏              *\n");
    printf("\t\t*              2、游戏规则              *\n");
    printf("\t\t*              3、退出游戏              *\n");
    printf("\t\t*****************************************\n");
    printf("请输入1或2或3:[ ]\b\b");
    scanf("%d", &n);
    switch (n)
    {
    case 1:
        Gameplay();                                                         //游戏开始函数
        break;
    case 2:
        explation();                                                       //游戏规则函数
        break;
    case 3:
        close();                                                          //关闭游戏函数
        break;
    }
}
int main()
{
    int j, i;
    for (j = 0; j < 4; j++)             //对4*4进行初始赋值为0
        for (i = 0; i < 4; i++)
            num[j][i] = 0;
    gamew = 0;                        //游戏获胜的判断变量初始化
    gamef = 0;                       //游戏失败的判断变量初始化
    ifappear = 0;                   //判断是否应该随机出现2或4的变量初始化
    score = 0;                     //游戏得分变量初始化
    gameover = 0;                 //游戏是否结束的变量初始化
    move = 0;                    //游戏的移动步数初始化
    menu();                     //调用主菜单函数
    return 0;
}
