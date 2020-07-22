# Day5_project
//편집기로 notepad++, winmerge(비교프로그램)소스코드 비교할 때
#include<stdio.h>
#include <Windows.h>

enum CharacterClass //열거형 ~를 열거한다.
{
	None = 0,
	Cleric, //성직자
	Warrior,    //전사
	Magician,   //마법사
	Archer,     //궁수
	Thief     //도적 
	//열거형이라는 하나의 타입을 정의를 한 것이다.(이름만 가질 수 있음)
	//성직자 다음으로는 워리어가 2 마법사가 3 순차적으로 숫자를 가진다
};


//	CharacterClass CharType = None;
//
//	CharType = Cleric;
//	printf("CharacterClass = %d\n",(int)CharType);
//
//	CharType = Warrior;
//	printf("CharacterClass = %d\n", (int)CharType);
//
//	CharType = Magician;
//	printf("CharacterClass = %d\n", (int)CharType);
//
//	CharType = Archer;
//	printf("CharacterClass = %d\n", (int)CharType);
//
//	CharType = Thief;
//	printf("CharacterClass = %d\n", (int)CharType);
//
//


int main()
{

	
	////반복문 while은 조건식 밖에 없다.
	//while (index < 10)
	//{
	//	if (index == 6)
	//	{

	//		break;
	//	}

	//	printf("반혹회수 : %d\n", index++); //뒤에 쓴 ++은 일딴 입력하고 그 후에 +1이 된다.
	//	//숫자의 시작은 무조건 0이라고 생각한다.

	//}
	int index = 0;
	CharacterClass job;
	
	bool bContinue = true;

	while (bContinue)
	{
		Sleep(1000);//일정 시간 동안 작업을 대기 하고싶을 때 사용(밀리초)
		system("cls");//이미 띄운 화면지우기
		printf("1) 성직자, 2)전사, 3)마법사, 4) 궁수, 5) 도적 \n");
		printf("직업을 선택해 주세요 : \n");
		scanf("%d", &job);

		bContinue = false;
		switch (job)
		{
		case CharacterClass::Cleric:
			printf("성직자를 선택하였습니다. \n");
			break;
		case CharacterClass::Warrior:
			printf("전사 선택하였습니다. \n");
			break;
		case CharacterClass::Magician:
			printf("마법사 선택하였습니다. \n");
			break;
		case CharacterClass::Archer:
			printf("궁수 선택하였습니다. \n");
			break;
		case CharacterClass::Thief:
			printf("도적 선택하였습니다. \n");
			break;
		default:
			printf("잘못 선택 하셨습니다.\n");
			bContinue = true;//다시 switch문을 돌린다.
			break;
		}
	}
	printf("Program is end! \n");

}

//#include<stdio.h>
//
////피보나치 수열
////F(0) = 0; 1
////F(1) = 1; 2
////0 1 1 2 3 5 8 13
//
//
//int Fionacci(int num)
//{
//	if (num <= 0)
//		return 0;
//	else if (num <= 2)
//		return 1;
//	else
//		return Fionacci(num - 1) + Fionacci(num - 2);//재귀  2개를 호출
//
//}
//
//int main()
//{
//	int num = 0;
//	printf("몇번째 항까지 출력? : ");
//
//	scanf_s("%d", &num,sizeof(num));
//	//반복문
//	// for(;반복문; )
//
//
//	for (int i = 0; i < num; i++)
//	{
//		printf("%d, ", Fionacci(i));
//
//	}
//
//	return 0;
//	//rename = f2(이름바꾸기)
//
//
//}


#include<stdio.h>
#include<time.h>
#include<Windows.h>

//
//int main()
//{
//
//	srand((unsigned int)time(NULL));
//	//언사인드 int로 캐스팅을 했다.0과 같으나 NULL이 가독성이 좋다
//	//seed+random = srand;
//
//	//while반복문 (처음에 시작부터 함)
//	//int index = 0;
//	//while (index < 10)
//	//{
//	//	printf("random num : %d \n",rand() % 10);
//	//	index++;
//
//	//}
//
//
//	// 랜덤 씨드를 헌재 시간으로 셋팅
//	//int index = 0;
//
//
//	////do while반복문 (일단 먼저 시작은 한다)
//	//do
//	//{
//	//	printf("index : %d \n",index);
//	//} while (index++ < 0);
//
//
//	return 0;
//}



//실습 
//#  0 ~ 39를 입력 받아서 scanf
//추첨을 통해 1~3등까지 추첨해서 출력
//3등이 되신것을 축하합니다.
//2등이 되신것을 축하합니다.
//1등이 되신것을 축하합니다.
//꽝 = > 다음기회에 다시 도전하세요 

int main()
{
	int num = 0;
	int randnum = 0;
	int timenum = 3;
	int index = 0;
	int count = 0;

	while (true)
	{

		srand((unsigned int)time(NULL));


		printf("0~39까지 숫자를 입력하세요. --> ");
		scanf("%d", &num);
		
		randnum = rand() % 40;

		if (randnum == num)
		{
			printf("%d등이 되신 것을 축하합니다.", timenum--);
			
		}
		else
		{
			printf("꽝 = > 다음기회에 다시 도전하세요 \n");
			printf("당첨된 숫자는 %d입니다.\n", randnum);

		}

		if (count == 2)
			break;
		count++;

	}



}

//숙제 2
//년도를 입력받아서 윤년(양력)인지 아닌지 출력


//숙제 3
//입력받은 명 수까지 주사위 굴리기

//-참여할 인원의 숫자를 입력
//-주사위의 최대 숫자를 얼마로 할건인지 입력
//-가장 큰 수가 당첨
//-몇번째 사람이 당첨이되었는지 인덱스(0부터) 출력
