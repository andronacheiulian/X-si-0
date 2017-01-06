# X-si-0
#include <iostream>
#include <conio.h>
#include <time.h>

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
	cout << "Alegeti numarul campului: \n";
	do {
		a = _getche();
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
	int R, OK;
	do {
		OK = 1;
		R = rand() % 9 + 1;
		if (R == 1 && matPoz[0] == '1')
			matPoz[0] = jucator;
		else if (R == 2 && matPoz[1] == '2')
			matPoz[1] = jucator;
		else if (R == 3 && matPoz[2] == '3')
			matPoz[2] = jucator;
		else if (R == 4 && matPoz[3] == '4')
			matPoz[3] = jucator;
		else if (R == 5 && matPoz[4] == '5')
			matPoz[4] = jucator;
		else if (R == 6 && matPoz[5] == '6')
			matPoz[5] = jucator;
		else if (R == 7 && matPoz[6] == '7')
			matPoz[6] = jucator;
		else if (R == 8 && matPoz[7] == '8')
			matPoz[7] = jucator;
		else if (R == 9 && matPoz[8] == '9')
			matPoz[8] = jucator;
		else
			OK = 0;

	} while (!OK);

}

void singlePlayerEasy()
{
	int scorX=0, scorO=0, nrJocuri=0;
	char tura, play = '1';
	do {
		cout << "| Apasati 1 pentru a incepe primul |\n";
		cout << "| Apasati 2 pentru a incepe al doilea |\n";
		tura = _getche();
		while (tura != '1'&&tura != '2')
		{
			cout << "Optiune incorecta, incercati din nou: ";
			tura = _getche();
			system("CLS");
			cout << "| Apasati 1 pentru a incepe primul |\n";
			cout << "| Apasati 2 pentru a incepe al doilea |\n";

		}
		if (tura == '1')
			jucator = 'X';
		else
			jucator = 'O';
		if (tura == '1')
		{
			while (testCastig() != 'X'&&testCastig() != 'O')
			{
				system("CLS");
				masaJoc(matPoz);
				cout << "| Este randul dumneavoastra |"<<endl;
				alegere();
				if (tablaPlina())
					break;
				schimbareJucator();
				mutariComp();
				if (tablaPlina())
					break;
				schimbareJucator();

			}
		}
		else if (tura == '2')
		{
			while (testCastig() != 'X'&&testCastig() != 'O')
			{
				mutariComp();
				if (tablaPlina())
					break;
				system("CLS");
				masaJoc(matPoz);
				if (testCastig() == 'X' || testCastig() == 'O')
					break;
				schimbareJucator();
				cout << "| Este randul dumneavoastra |"<<endl;
				alegere();
				if (tablaPlina())
					break;
				schimbareJucator();
			}
		}
		if (testCastig() == 'X')
		{
			scorX++;
			nrJocuri++;
			cout << "***Felicitari, ai castigat!***"<<endl;

		}
		else if (testCastig() == 'O')
		{
			scorO++;
			nrJocuri++;
			cout << "***Calculatorul a castigat!***"<<endl;

		}
		else if (tablaPlina())
		{
			nrJocuri++;
			cout << "***Remiza!***"<<endl;

		}



	} while (play == '1');
	system("CLS");

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
