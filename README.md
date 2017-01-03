# X-si-0
#include <iostream>
#include <conio.h>

using namespace std;
char matPoz[10] = {'1','2','3','4','5','6','7','8','9'};
char nume1[30], nume2[30];

char meniu()
{
	cout << "          X si 0\n" << endl;
	cout << "   1.Joc nou- Single Player\n";
	cout << "   2.Joc nou- Multiplayer\n";
	cout << "   3.Informatii joc\n";
	cout << "   4.Iesire\n";
	cout << "\n\nAlegeti optiunea: ";
	return _getche();
}

void masaJoc(char[])
{
	cout << "\n  -----X SI 0-----" << endl << endl;
	cout <<"\n      "<< nume1 << " vs " << nume2<<"\n"<<endl<<endl;
	cout << "       |   |     " << endl;
	cout <<"     "<<matPoz[0] << " | " << matPoz[1] << " | " << matPoz[2] << endl;
	cout << "    ___|___|___" << endl;
	cout << "       |   |     " << endl;
	cout << "     " << matPoz[3] << " | " << matPoz[4] << " | " << matPoz[5] << endl;
	cout << "    ___|___|___" << endl;
	cout << "       |   |     " << endl;
	cout << "     " << matPoz[6] << " | " << matPoz[7] << " | " << matPoz[8] << endl;
	cout << "       |   |     " << endl;

}

int main()
{
	int x;
	system("color b");
	while (1)
	{
		switch (meniu()) {
		case '1':
			system("CLS");
			cout << "\nAlegeti numele dumneavoastra: ";
			cin >> nume1;
			cout << "Alegeti numele calculatorului: ";
			cin >> nume2;
			fflush(stdin);
			masaJoc(matPoz);

			cin >> x;
		case '2':
			cout << "info";
		case'3':
			cout << "info";
		case '4':
			exit(0);
		default:
			cout << "\nOptiune inexistenta!";
		}
		_getch();
	}
	cin >> x;

	return 0;
}
