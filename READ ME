#include <stdio.h>
#include <windows.h>
#include <conio.h>
// 상대방 먼저먹으면 이김


//int getnum();

int main(void)
{
	char map[10][10] = { 0, }; // 보여지는 맵

	int x[2], y[2]; //x좌표와 y좌표

	char player1, player2; // 플레이어

	int move[2]; // 키값 받는거

	char yes;
	//int mop_move = 9; // 몹 위치 x좌표

	printf("========================\n");
	printf("=                      =\n");
	printf("=      EAT THAT!       =\n");
	printf("=                      =\n");
	printf("========================\n");



RESTART:
	for (int i = 0; i < 10; i++)
	{
		for (int j = 0; j < 10; j++)
		{
			map[i][j] = ' '; // 0으로 하면 드러워서 스페이스바로 모두 초기화
		}
	}
	Sleep(2000);
	system("cls");
	for (int i = 0; i < 10; i++)
	{
		for (int j = 0; j < 10; j++)
		{
			printf("[%c]", map[i][j]); // 기본적인 맵을 보여줌
		}
		printf("\n");
	}



	printf("플레이어 1이 화살표, 2가 WASD입니다\n");
	printf("내가 코드를 이상하게 짜서..\n\n");


	printf("플레이어1을 소환해주세요 (x좌표 y좌표 캐릭터(알파벳))\n"); // 캐릭터 소환
	printf("예 : 8 8 A\n");

XY_INPUT_AGAIN_P1:
	scanf_s("%d %d %c", &x[0], &y[0], &player1);

	if (x[0] > 9 || y[0] > 9)
	{
		printf("0~9 사이로 입력해주세요\n"); //배열이 0부터 9까지임
		goto XY_INPUT_AGAIN_P1;
	}






	printf("플레이어2를 소환해주세요 (다른 좌표에 소환)\n"); // 캐릭터 소환
	printf("예 : 1 1 B\n");

XY_INPUT_AGAIN_P2:
	scanf_s("%d %d %c", &x[1], &y[1], &player2);

	if (x[1] > 9 || y[1] > 9)
	{
		printf("0~9 사이로 입력해주세요\n"); //배열이 0부터 9까지임
		goto XY_INPUT_AGAIN_P2;
	}






	map[y[0]][x[0]] = player1;//플레이어 모양 정하기
	map[y[1]][x[1]] = player2;

	while (1)//게임 시작!
	{
		//Sleep(10);
		system("cls"); // 콘솔창 싹쓸이
		//random_position = (rand() % 10) + 1;
		//random_position -= 1;
		//backmap[random_position][9] = 1;
		//map[random_position][9] = '*'; // 별 저장


		for (int i = 0; i < 10; i++)
		{
			for (int j = 0; j < 10; j++)
			{
				printf("[%c]", map[i][j]); // 플레이어가 들어가 있는 맵 표기
			}
			printf("\n");
		}

		if (x[1] == x[0] && y[1] == y[0]) // 잡았는지 확인함
			break;


		move[1] = _getch(); // 넘패드 8 4 5 6 받음

		switch (move[1]) // p2 무빙
		{
		case 119: // 상
			if (y[1] != 0)
			{
				map[y[1] - 1][x[1]] = player2;
				map[y[1]][x[1]] = ' ';
				y[1] -= 1;
			}
			break;
		case 97: // 좌
			if (x[1] != 0)
			{
				map[y[1]][x[1] - 1] = player2;
				map[y[1]][x[1]] = ' ';
				x[1] -= 1;
			}
			break;
		case 115: // 하
			if (y[1] != 9)
			{
				map[y[1] + 1][x[1]] = player2;
				map[y[1]][x[1]] = ' ';
				y[1] += 1;
			}
			break;
		case 100: // 우
			if (x[1] != 9)
			{
				map[y[1]][x[1] + 1] = player2;
				map[y[1]][x[1]] = ' ';
				x[1] += 1;
			}
			break;
		}

		if (move[1] != 119 && move[1] != 97)
			if (move[1] != 115 && move[1] != 100)
				move[0] = _getch(); // 화살표값 받음

		switch (move[0]) // p1 무빙
		{
		case 72: // 상
			if (y[0] != 0)
			{
				map[y[0] - 1][x[0]] = player1;
				map[y[0]][x[0]] = ' ';
				y[0] -= 1;
			}
			break;
		case 75: // 좌
			if (x[0] != 0)
			{
				map[y[0]][x[0] - 1] = player1;
				map[y[0]][x[0]] = ' ';
				x[0] -= 1;
			}
			break;
		case 80: // 하
			if (y[0] != 9)
			{
				map[y[0] + 1][x[0]] = player1;
				map[y[0]][x[0]] = ' ';
				y[0] += 1;
			}
			break;
		case 77: // 우
			if (x[0] != 9)
			{
				map[y[0]][x[0] + 1] = player1;
				map[y[0]][x[0]] = ' ';
				x[0] += 1;
			}
			break;
		}
		move[1] = 0;
		move[0] = 0;
		//



		//backmap[random_position][mop_move] = 0;
		//backmap[random_position][mop_move - 1] = 1;
		//map[random_position][mop_move] = ' ';
		//map[random_position][mop_move - 1] = '*';


	}
	printf("게임오버!\n");
	if (map[y[0]][x[0]] == player1)
		printf("%c 가 %c를 먹었습니다!\n", player1, player2);
	else if (map[y[0]][x[0]] == player2)
		printf("%c 가 %c를 먹었습니다!\n", player2, player1);
	printf("다시 하쉴? (Y/N)\n");
ASK:

	scanf_s("%c", &yes);

	if (yes == 'Y')
	{
		system("cls");
		printf("========================\n");
		printf("=                      =\n");
		printf("=     가즈아아아아!    =\n");
		printf("=                      =\n");
		printf("========================\n");
		Sleep(2000);
		system("cls");
		goto RESTART;
	}
	else if (yes == 'N')
	{
		printf("잘가..\n");
		return 0;
	}
	else goto ASK;
}
