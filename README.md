# X-si-0
#include <iostream>
#include <conio.h>

using namespace std;
char jucator = 'X';
char matPoz[9]= {'1','2','3','4','5','6','7','8','9'};
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
	cout <<"\n     "<< nume1 << " vs " << nume2<<"\n"<<endl<<endl;
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

void schimbareJucator()
{
	if (jucator == 'X')
		jucator = '0';
	else
		jucator = 'X';
}

void alegere()
{
	int esteValid;
	char a;
	cout << "Alegeti numarul campului: ";
	do {
		cin >> a;
		esteValid = 1;
		if (a == '1' && matPoz[0] == '1')
			matPoz[0] = jucator;
		else if (a == '2' && matPoz[1] == '2')
			matPoz[1] = jucator;
		else if (a == '3' && matPoz[2] == '3')
			matPoz[2] = jucator;
		else if (a == '4' && matPoz[3] == '4')
			matPoz[3] = jucator;
		else if (a == '5' && matPoz[4] == '5')
			matPoz[4] = jucator;
		else if (a == '6' && matPoz[5] == '6')
			matPoz[5] = jucator;
		else if (a == '7' && matPoz[6] == '7')
			matPoz[6] = jucator;
		else if (a == '8' && matPoz[7] == '8')
			matPoz[7] = jucator;
		else if (a == '9' && matPoz[8] == '9')
			matPoz[8] = jucator;
		else
		{
			cout<<"Optiune incorecta, incercati din nou: ";
			esteValid = 0;
		}


	} while (!esteValid);
}

int testCastig()
{
	if (matPoz[0] == 'X'&&matPoz[1] == 'X'&&matPoz[2] == 'X')
		return 'X';
	if (matPoz[3] == 'X'&&matPoz[4] == 'X'&&matPoz[5] == 'X')
		return 'X';
	if (matPoz[6] == 'X'&&matPoz[7] == 'X'&&matPoz[8] == 'X')
		return 'X';
	if (matPoz[0] == 'X'&&matPoz[3] == 'X'&&matPoz[6] == 'X')
		return 'X';
	if (matPoz[1] == 'X'&&matPoz[4] == 'X'&&matPoz[7] == 'X')
		return 'X';
	if (matPoz[2] == 'X'&&matPoz[5] == 'X'&&matPoz[8] == 'X')
		return 'X';
	if (matPoz[0] == 'X'&&matPoz[4] == 'X'&&matPoz[8] == 'X')
		return 'X';
	if (matPoz[2] == 'X'&&matPoz[4] == 'X'&&matPoz[6] == 'X')
		return 'X';
	if (matPoz[0] == 'O'&&matPoz[1] == 'O'&&matPoz[2] == 'O')
		return 'O';
	if (matPoz[3] == 'O'&&matPoz[4] == 'O'&&matPoz[5] == 'O')
		return 'O';
	if (matPoz[6] == 'O'&&matPoz[7] == 'O'&&matPoz[8] == 'O')
		return 'O';
	if (matPoz[0] == 'O'&&matPoz[3] == 'O'&&matPoz[6] == 'O')
		return 'O';
	if (matPoz[1] == 'O'&&matPoz[4] == 'O'&&matPoz[7] == 'O')
		return 'O';
	if (matPoz[2] == 'O'&&matPoz[5] == 'O'&&matPoz[8] == 'O')
		return 'O';
	if (matPoz[0] == 'O'&&matPoz[4] == 'O'&&matPoz[8] == 'O')
		return 'O';
	if (matPoz[2] == 'O'&&matPoz[4] == 'O'&&matPoz[6] == 'O')
		return 'O';
	else
		return 0;


}

int tablaPlina()
{
	if (matPoz[0] != '1'&&matPoz[1] != '2'&&matPoz[2] != '3'&&matPoz[3] != '4'&&matPoz[4] != '5'&&matPoz[5] != '6'&&matPoz[6] != '7'&&matPoz[7] != '8'&&matPoz[8] != '9')
		return 1;
	return 0;
}

void mutariComp()
{
	int R, adev;

}

void singlePlayerEasy()
{
	int scorX=0, scorO=0, nrJocuri=0;
	char tura, play = '1';


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
			cout << "Alegeti nivelul de dificultate: ";
			cout << "\nEasy(1)";
			cout << "\nHard(2)"<<endl;
			if (_getch() == '1')
			{
				fflush(stdin);
				masaJoc(matPoz);
				alegere();
				singlePlayerEasy();

			}
			else if (_getch() == '2')
				cout << "hard";
			else
				cout << "Optiune incorecta";
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
