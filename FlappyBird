#include"stdio.h"
#include"windows.h"
#include"string.h"
#include"conio.h"
#include"time.h"

typedef struct pipe
{
	int x;
	int y;
	struct pipe *next;
}PIPE;

char backGround[14][80] = {0};
int  Time = 0;
unsigned int  Score = 0;

void HideCursor()
{
	CONSOLE_CURSOR_INFO cursor_info = {1, 0};
	SetConsoleCursorInfo(GetStdHandle(STD_OUTPUT_HANDLE), &cursor_info);
}

void gotoxy(int x, int y)
{
	COORD coord;
	coord.X = x;
	coord.Y = y;
	SetConsoleCursorPosition(GetStdHandle(STD_OUTPUT_HANDLE), coord);
}

void Getready()
{
	int i = 0, j = 0;

	for(i = 0; i < 11; i++)
	{
		for(j = 0; j < 80; j++)
		{
			backGround[i][j] = ' ';
		}
	}
	for(i = 0; i < 8; i++)
	{
		strcat(backGround, "  ┌┐    ");
	}
	for(i = 0; i < 8; i++)
	{
		strcat(backGround, "┌┤│    ");
	}
	for(i = 0; i < 8; i++)
	{
		strcat(backGround, "││├┐  ");
	}
	puts(backGround);

	gotoxy(30, 3);
	printf("G e t  R e a d y");
	
	gotoxy(0, 14);
	for(i=0; i < 40; i++)
	{
		printf("▁");	
	}
	for(i = 0; i < 11; i++)
	{
		printf("  ╱╱ ");
	}
	gotoxy(0, 16);
	for(i = 0; i < 40; i++)
	{
		printf("▔");
	}
	gotoxy(18, 3);
	printf("*@>");
	getch();
	gotoxy(30, 3);
	printf("                ");



}

PIPE *Pipefun(PIPE *h)
{
	int i = 0, j = 0;
	PIPE *p;

	for(p = h, i = 0; i<6; i++)
	{	
		for(j = 0; j<14; j++)
		{
			if( j == p->y-1 || j == p->y || j == p->y+1  )
				continue;
			else
			{
				if(p->x >= 0 && p->x < 80)
					gotoxy(p->x, j),printf("■");
				if(p->x+2 >= 0 && p->x+2 < 80)
					gotoxy(p->x+2, j),printf("■");
				if(p->x+4 >= 0 && p->x+4 < 80)
					gotoxy(p->x+4, j), printf("%c%c",backGround[j][p->x+4],backGround[j][p->x+5]);
			}
		}
		p->x = p->x-2;
		p = p->next ;
	}

	if(h->x < -4)
	{
		h->x = 78+12;
		h->y = rand()%9+3;
		h = h->next;
	}
	
	return h;
}

void Bird()
{
	int  i = 0, bird = 3, temp = 0;
	char ch = '0';
	PIPE *h, *p, *q;

	p = h = q = (PIPE *)malloc(sizeof(PIPE));
	for(i = 0; i < 5; i++)
	{
		p->x = 78+16*i;
		p->y = rand()%9+3;
		q = (PIPE *)malloc(sizeof(PIPE));
		p->next = q;
		q->next = NULL;
		p = q;
	}
	p->x = 78 + 16 * i;
	p->y = rand() %13 + 1;
	q->next = h;

	while(1)
	{
		Time++;

		temp = bird;

		if(kbhit())
			ch=getch();

		ch == ' ' ? bird-- : bird++;
		ch = '0';

		if(bird < 0 || bird >= 14)
			break;

		gotoxy(18, temp);
		printf("  %c%c", backGround[temp][20], backGround[temp][21]);
		gotoxy(18, bird);
		printf("*@>");
		
		if(Time%3 == 1)
			h = Pipefun(h);
		for(p = h, i = 0; i<6; i++, p = p->next)
			if(p->x == 18 && p->y-1 != bird && p->y != bird && p->y+1 != bird)
				break;
		if(p->x == 18 && p->y-1 != bird && p->y != bird && p->y+1 != bird)
			break;
			
		Sleep(300);
	}
}

void Gameover()
{
	Score = (Time - 88) / 24 < 0 ? 0 : (Time - 88) / 24;
	gotoxy(28, 5);
	printf("┌──────────┐");
	gotoxy(28, 6);
	printf("│   G A M E O V E R  │");
	gotoxy(28, 7);
	printf("│                    │");
	gotoxy(28, 8);
	printf("│             %4d   │",Score);
	gotoxy(28, 9);
	printf("└──────────┘");

}

int main()
{
	HideCursor();
	system("title Flappy Bird");
	system("mode con cols = 80 lines = 20");
	srand((unsigned)time(NULL));

	Getready();
	Bird();
	Gameover();

	getch();
}
