#include <stdio.h>
#include <stdlib.h>
#include <windows.h>

//水平方向为x，竖直方向为y

int main()
{
	int i, j;
	int x = 15;
	int y = 1;
	int velocity_x = 1;
	int velocity_y = 1;

	//上下左右边界
	int left = 0;
	int right =25;
	int top = 0;
	int bottom = 25;

	while (1)
	{
		x = x + velocity_x;
		y = y + velocity_y;

		system("cls");//清屏

		//输出小球前的空行
		for (i = 0; i < y; ++i)
		{
			printf("\n");
		}
		for (j = 0; j < x; j++)
		{
			printf(" ");
		}
		printf("o\n");//输出小球o
		Sleep(50);
		
		//触壁响铃
		if (x == left || x == right || y == top || y == bottom)
		{
			printf("\a");
		}

		//越界判断
		if (y <= top || y >= bottom)
		{
			velocity_y = -velocity_y;
		}
		if (x <= left || x >= right)
		{
			velocity_x = -velocity_x;
		}
	}

// 	system("pause");
	return 0;
}
