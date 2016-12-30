# X-si-0
#include <iostream>
#include <conio.h>

using namespace std;

char meniu()
{
	cout << "1.Joc nou- Single Player\n";
	cout << "2.Joc nou- Multiplayer\n";
	cout << "3.Informatii joc\n";
	cout << "4.Iesire\n";
	cout << "\n\nAlegeti optiunea: ";
	return _getche();
}

int main()
{
	while (1)
	{
		system("cls");
		switch (meniu()) {
		case '1':
			fflush(stdin);
			cout << "in lucru";
		case '2':
			cout << "si mai in lucru";
		case'3':
			cout << "aici e mai ok, trebuie niste info";
		case '4':
			exit(0);
		default:
			cout << "\nOptiune inexistenta!";
		}
		_getch();
	}

	return 0;
}
