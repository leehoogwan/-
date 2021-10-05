#include<iostream>
#include<string>
//#include<cmath>

using namespace std;

enum VERSION
{
	PRINT,
	SEARCH,
	CALCULATE,
	PERIOD
};


int main()
{
	string arr[22] = { "a", "수소", "헬륨", "리튬", "베릴륨", "붕소", "탄소", "질소", 
		"산소","플루오르", "네온", "나트륨", "마그네슘", "알루미늄", "규소", 
		"인", "황", "염소", "아르곤", "칼륨", "칼슘" };  //원소 저장을 위한 배열
														 //0번 자리에 임의의 문자 넣음(안쓸거라서)
	string ar[22] = { "안씀", "H", "He", "Li", "Be", "B", "C", "N",
						"O", "F", "Ne", "Na", "Mg", "Al", "Si",
							"P", "S", "Cl", "Ar", "K", "Ca"};

	while (true)
	{
		system("cls");

		cout << "=================================" << endl;

		cout << "주기율표 프로그램 VER.1" << endl;
		cout << endl;

		cout << "1. 전체 주기율표 출력 (1~20)" << endl;
		cout << "2. 원소 검색" << endl;
		cout << "3. 원자가전자 개수 계산" << endl;
		cout << "4. 주기 계산" << endl << endl;

		cout << "=================================" << endl;
		cout << "원하는 기능을 선택해 주세요. -> ";

		int menu;
		cin >> menu;
		menu = menu -1 ;

		if (cin.fail())
		{
			cin.clear();
			cin.ignore(1024, '\n');
			continue;
		}

		string C;
		int k;

		switch (menu)
		{
		case(PRINT):
			system("cls");

			cout << "주기율표 전체 출력 메뉴입니다." << endl;
			for (int i = 1; i <= 20; i++)
			{
				cout << i << "번 " << arr[i] << endl;
			}

			system("pause");
			break;
			
		case(SEARCH):
			while (1)
			{
				system("cls");
				cout << "원소 검색 메뉴입니다." << endl;
				cout << "원소 이름을 입력해 주세요.->";
				cin >> C;

				for (int i = 1; i <= 20; i++)
				{
					if (arr[i] == C)
					{
						cout << arr[i] << "의 원자번호 : " << i << endl;
						cout << arr[i] << "의 원소기호 : " << ar[i] << endl;
					}
					else
					{
						cout << "해당 원소가 존재하지 않습니다." << endl;
						break;
					}
				}

				system("pause");
				break;
			}
			break;

		case(CALCULATE):

			system("cls");

			cout << "원자가전자 개수 계산 메뉴입니다." << endl;
			cout << "원자번호를 입력해주세요. (수소, 헬륨 제외) -> ";
			cin >> k;
			cout << k << "번 원소의 원자가전자는 " << (k - 2) % 8 << "개" << endl;

			system("pause");
			break;

		case(PERIOD):
			system("cls");
			cout << "주기 계산 메뉴입니다." << endl;
			cout << "원자번호를 입력해주세요. ->";
			cin >> k;
			cout << k << "번 원소는 " << (k / 8) + 1 << "주기 원소" << endl;
			system("pause");
			break;
		}

	
	}
	
	return 0;
}

