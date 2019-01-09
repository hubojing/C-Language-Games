#include <stdio.h>
#include <stdlib.h>
#include <windows.h>
#include <conio.h>

int main()
{
	int i, j;
	int x = 5;
	int y = 10;
	char input;
	int target_x = 5;
	int target_y = 5;

	int isFired = 0;
	int isKilled = 0;

	while (1)
	{
		system("cls");

		//如果没击中靶子，就显示靶子
		if (isKilled == 0)
		{
			for (i = 0; i < target_y; ++i)
			{
				printf("\n");
			}
			for (i = 0; i < target_x; ++i)
			{
				printf(" ");
			}

			printf("+\n");

		}

		if (isFired == 0)
		{
			for (i = 0; i < y; ++i)
			{
				printf("\n");
			}
		}
		else//如果开火，有竖线
		{
			for (i = 0; i < y; ++i)
			{
				for (j = 0; j < x; ++j)
				{
					printf(" ");
				}
				printf("  |\n");
			}

			if (x + 2 == target_x)
			{
				isKilled = 1;
			}

			isFired = 0;
		}
		for (j = 0; j < x; ++j)
		{
			printf(" ");
		}
		printf("  *\n");
		for (i = 0; i < x; ++i)
		{
			printf(" ");
		}
		printf("*****\n");
		for (i = 0; i < x; ++i)
		{
			printf(" ");
		}
		printf(" * *\n");

// 		scanf("%c", &input);按回车*才会移动
		input = getch();//实时移动

		//飞机上下左右移动
		if (input == 's')
		{
			y++;
		}
		if (input == 'w')
		{
			y--;
		}
		if (input == 'a')
		{
			x--;
		}
		if (input == 'd')
		{
			x++;
		}

		//按空格射击
		if (input == ' ')
		{
			isFired = 1;
		}

	}

//system("pause");
}
