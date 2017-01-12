# X-si-0
#include <iostream>
#include <conio.h>
#include <time.h>


using namespace std;
char jucator = 'X';
char matPoz[9]= {'1','2','3','4','5','6','7','8','9'};
char exemplu[9] = { 'X','O','O','O','X','6','O','8','X' };
char nume1[30], nume2[30];
int joc = 2;

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

void masaJoc(char x[])
{
	cout << "\n  -----X SI 0-----" << endl << endl;
	cout <<"\n     "<< nume1 << " vs " << nume2<<"\n"<<endl<<endl;
	cout << "       |   |     " << endl;
	cout <<"     "<<x[0] << " | " << x[1] << " | " << x[2] << endl;
	cout << "    ___|___|___" << endl;
	cout << "       |   |     " << endl;
	cout << "     " << x[3] << " | " << x[4] << " | " << x[5] << endl;
	cout << "    ___|___|___" << endl;
	cout << "       |   |     " << endl;
	cout << "     " << x[6] << " | " << x[7] << " | " << x[8] << endl;
	cout << "       |   |     " << endl;

}

void schimbareJucator()
{
	if (jucator == 'X')
		jucator = 'O';
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
		srand(time(0));
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
void scor(int a, int b, int c, char *nume1, char *nume2)
{
	cout << "| Scor " << nume1 << ": " << a << "      |" << endl;
	cout << "| Scor " << nume2 << ": " << b << "      |" << endl;
	cout << "| Numar jocuri: " << c << " |" << endl;

}

void scor2(int a, int b, int c, char *nume1)
{
	cout << "| Scor " << nume1 << ": " << a << "              |" << endl;
	cout << "| Scor calculator: " << b << "      |" << endl;
	cout << "| Numar jocuri: " << c << "         |" << endl;
}

void scor3(int a, int b, int c, char *nume1)
{
	cout << "| Scor " << nume1 << ": " << a << "              |" << endl;
	cout << "| Scor calculator: " << b << "      |" << endl;
	cout << "| Numar jocuri: " << c << "         |" << endl;
}

void reset()
{
	matPoz[0] = '1';
	matPoz[1] = '2';
	matPoz[2] = '3';
	matPoz[3] = '4';
	matPoz[4] = '5';
	matPoz[5] = '6';
	matPoz[6] = '7';
	matPoz[7] = '8';
	matPoz[8] = '9';
	jucator = 'X';
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
			cout << "\n----------------------------------" << endl;
			cout << "| ***Felicitari, ai castigat!*** |"<<endl;
			cout << "----------------------------------" << endl;

		}
		else if (testCastig() == 'O')
		{
			scorO++;
			nrJocuri++;
			cout << "\n----------------------------------" << endl;
			cout << "| ***Calculatorul a castigat!*** |" << endl;
			cout << "----------------------------------" << endl;

		}
		else if (tablaPlina())
		{
			nrJocuri++;
			cout << "\n-----------------" << endl;
			cout << "| ***Remiza!*** |" << endl;
			cout << "-----------------" << endl;
		}
		scor2(scorX, scorO, nrJocuri, nume1);
		cout << "-------------------------------------------------" << endl;
		cout << "| Apasati 1 pentru a juca din nou               |" << endl;
		cout << "| Apasati 2 pentru a reveni la meniul principal |" << endl;
		cout << "| Apasati 3 pentru a iesi                       |" << endl;
		cout << "-------------------------------------------------" << endl;
	eticheta:
		play = _getche();
		if (play == '1')
		{
			reset();
			system("CLS");
		}
		else if (play == '2')
		{
			joc = 2;
			reset();
			system("CLS");
			meniu();
		}
		else if (play == '3')
			exit(0);
		else
		{
			system("CLS");
			cout << "-------------------------------------------------" << endl;
			cout << "| Apasati 1 pentru a juca din nou               |" << endl;
			cout << "| Apasati 2 pentru a reveni la meniul principal |" << endl;
			cout << "| Apasati 3 pentru a iesi                       |" << endl;
			cout << "-------------------------------------------------" << endl;
			cout << "Optiune incorecta, incercati din nou: " << endl;
			goto eticheta;
		}
	} while (play == '1');
	system("CLS");
}

void mutariCompHard()
{
	int R, OK;
	if (matPoz[0] == 'X'&&matPoz[1] == 'X'&&matPoz[2] == '3')
		matPoz[2] = jucator;
	else if (matPoz[0] == 'X'&&matPoz[2] == 'X'&&matPoz[1] == '2')
		matPoz[1] = jucator;
	else if (matPoz[1] == 'X'&&matPoz[2] == 'X'&&matPoz[0] == '1')
		matPoz[0] = jucator;
	else if (matPoz[3] == 'X'&&matPoz[4] == 'X'&&matPoz[5] == '6')
		matPoz[5] = jucator;
	else if (matPoz[3] == 'X'&&matPoz[5] == 'X'&&matPoz[4] == '5')
		matPoz[4] = jucator;
	else if (matPoz[4] == 'X'&&matPoz[5] == 'X'&&matPoz[3] == '4')
		matPoz[3] = jucator;
	else if (matPoz[6] == 'X'&&matPoz[7] == 'X'&&matPoz[8] == '9')
		matPoz[8] = jucator;
	else if (matPoz[6] == 'X'&&matPoz[8] == 'X'&&matPoz[7] == '8')
		matPoz[7] = jucator;
	else if (matPoz[7] == 'X'&&matPoz[8] == 'X'&&matPoz[6] == '7')
		matPoz[6] = jucator;
	else if (matPoz[0] == 'X'&&matPoz[3] == 'X'&&matPoz[6] == '7')
		matPoz[6] = jucator;
	else if (matPoz[0] == 'X'&&matPoz[6] == 'X'&&matPoz[3] == '4')
		matPoz[3] = jucator;
	else if (matPoz[3] == 'X'&&matPoz[6] == 'X'&&matPoz[0] == '1')
		matPoz[0] = jucator;
	else if (matPoz[1] == 'X'&&matPoz[4] == 'X'&&matPoz[7] == '8')
		matPoz[7] = jucator;
	else if (matPoz[1] == 'X'&&matPoz[7] == 'X'&&matPoz[4] == '5')
		matPoz[4] = jucator;
	else if (matPoz[4] == 'X'&&matPoz[7] == 'X'&&matPoz[1] == '2')
		matPoz[1] = jucator;
	else if (matPoz[2] == 'X'&&matPoz[5] == 'X'&&matPoz[8] == '9')
		matPoz[8] = jucator;
	else if (matPoz[2] == 'X'&&matPoz[8] == 'X'&&matPoz[5] == '6')
		matPoz[5] = jucator;
	else if (matPoz[5] == 'X'&&matPoz[8] == 'X'&&matPoz[2] == '3')
		matPoz[2] = jucator;
	else if (matPoz[0] == 'X'&&matPoz[4] == 'X'&&matPoz[8] == '9')
		matPoz[8] = jucator;
	else if (matPoz[0] == 'X'&&matPoz[8] == 'X'&&matPoz[4] == '5')
		matPoz[4] = jucator;
	else if (matPoz[4] == 'X'&&matPoz[8] == 'X'&&matPoz[0] == '1')
		matPoz[0] = jucator;
	else if (matPoz[2] == 'X'&&matPoz[4] == 'X'&&matPoz[6] == '7')
		matPoz[6] = jucator;
	else if (matPoz[2] == 'X'&&matPoz[6] == 'X'&&matPoz[4] == '5')
		matPoz[4] = jucator;
	else if (matPoz[4] == 'X'&&matPoz[6] == 'X'&&matPoz[2] == '3')
		matPoz[2] = jucator;

	else if (matPoz[0] == 'O'&&matPoz[1] == 'O'&&matPoz[2] == '3')
		matPoz[2] = jucator;
	else if (matPoz[0] == 'O'&&matPoz[2] == 'O'&&matPoz[1] == '2')
		matPoz[1] = jucator;
	else if (matPoz[1] == 'O'&&matPoz[2] == 'O'&&matPoz[0] == '1')
		matPoz[0] = jucator;
	else if (matPoz[3] == 'O'&&matPoz[4] == 'O'&&matPoz[5] == '6')
		matPoz[5] = jucator;
	else if (matPoz[3] == 'O'&&matPoz[5] == 'O'&&matPoz[4] == '5')
		matPoz[4] = jucator;
	else if (matPoz[4] == 'O'&&matPoz[5] == 'O'&&matPoz[3] == '4')
		matPoz[3] = jucator;
	else if (matPoz[6] == 'O'&&matPoz[7] == 'O'&&matPoz[8] == '9')
		matPoz[8] = jucator;
	else if (matPoz[6] == 'O'&&matPoz[8] == 'O'&&matPoz[7] == '8')
		matPoz[7] = jucator;
	else if (matPoz[7] == 'O'&&matPoz[8] == 'O'&&matPoz[6] == '7')
		matPoz[6] = jucator;
	else if (matPoz[0] == 'O'&&matPoz[3] == 'O'&&matPoz[6] == '7')
		matPoz[6] = jucator;
	else if (matPoz[0] == 'O'&&matPoz[6] == 'O'&&matPoz[3] == '4')
		matPoz[3] = jucator;
	else if (matPoz[3] == 'O'&&matPoz[6] == 'O'&&matPoz[0] == '1')
		matPoz[0] = jucator;
	else if (matPoz[1] == 'O'&&matPoz[4] == 'O'&&matPoz[7] == '8')
		matPoz[7] = jucator;
	else if (matPoz[1] == 'O'&&matPoz[7] == 'O'&&matPoz[4] == '5')
		matPoz[4] = jucator;
	else if (matPoz[4] == 'O'&&matPoz[7] == 'O'&&matPoz[1] == '2')
		matPoz[1] = jucator;
	else if (matPoz[2] == 'O'&&matPoz[5] == 'O'&&matPoz[8] == '9')
		matPoz[8] = jucator;
	else if (matPoz[2] == 'O'&&matPoz[8] == 'O'&&matPoz[5] == '6')
		matPoz[5] = jucator;
	else if (matPoz[5] == 'O'&&matPoz[8] == 'O'&&matPoz[2] == '3')
		matPoz[2] = jucator;
	else if (matPoz[0] == 'O'&&matPoz[4] == 'O'&&matPoz[8] == '9')
		matPoz[8] = jucator;
	else if (matPoz[0] == 'O'&&matPoz[8] == 'O'&&matPoz[4] == '5')
		matPoz[4] = jucator;
	else if (matPoz[4] == 'O'&&matPoz[8] == 'O'&&matPoz[0] == '1')
		matPoz[0] = jucator;
	else if (matPoz[2] == 'O'&&matPoz[4] == 'O'&&matPoz[6] == '7')
		matPoz[6] = jucator;
	else if (matPoz[2] == 'O'&&matPoz[6] == 'O'&&matPoz[4] == '5')
		matPoz[4] = jucator;
	else if (matPoz[4] == 'O'&&matPoz[6] == 'O'&&matPoz[2] == '3')
		matPoz[2] = jucator;
	else
	{
		do {
			OK = 1;
			srand(time(0));
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


}

void singlePlayerHard()
{
	int scorX = 0, scorO = 0, nrJocuri = 0;
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
				cout << "| Este randul dumneavoastra |" << endl;
				alegere();
				if (tablaPlina())
					break;
				schimbareJucator();
				mutariCompHard();
				if (tablaPlina())
					break;
				schimbareJucator();

			}
		}
		else if (tura == '2')
		{
			while (testCastig() != 'X'&&testCastig() != 'O')
			{
				mutariCompHard();
				if (tablaPlina())
					break;
				system("CLS");
				masaJoc(matPoz);
				if (testCastig() == 'X' || testCastig() == 'O')
					break;
				schimbareJucator();
				cout << "| Este randul dumneavoastra |" << endl;
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
			cout << "\n----------------------------------" << endl;
			cout << "| ***Felicitari, ai castigat!*** |" << endl;
			cout << "----------------------------------" << endl;

		}
		else if (testCastig() == 'O')
		{
			scorO++;
			nrJocuri++;
			cout << "\n----------------------------------" << endl;
			cout << "| ***Calculatorul a castigat!*** |" << endl;
			cout << "----------------------------------" << endl;

		}
		else if (tablaPlina())
		{
			nrJocuri++;
			cout << "\n-----------------" << endl;
			cout << "| ***Remiza!*** |" << endl;
			cout << "-----------------" << endl;

		}
		scor3(scorX, scorO, nrJocuri, nume1);
		cout << "-------------------------------------------------" << endl;
		cout << "| Apasati 1 pentru a juca din nou               |" << endl;
		cout << "| Apasati 2 pentru a reveni la meniul principal |" << endl;
		cout << "| Apasati 3 pentru a iesi                       |" << endl;
		cout << "-------------------------------------------------" << endl;
	eticheta:
		play = _getche();
		if (play == '1')
		{
			reset();
			system("CLS");
		}
		else if (play == '2')
		{
			joc = 2;
			reset();
			system("CLS");
			meniu();
		}
		else if (play == '3')
			exit(0);
		else
		{
			system("CLS");
			cout << "-------------------------------------------------" << endl;
			cout << "| Apasati 1 pentru a juca din nou               |" << endl;
			cout << "| Apasati 2 pentru a reveni la meniul principal |" << endl;
			cout << "| Apasati 3 pentru a iesi                       |" << endl;
			cout << "-------------------------------------------------" << endl;
			cout << "Optiune incorecta, incercati din nou: " << endl;
			goto eticheta;
		}
	} while (play == '1');
	system("CLS");
}

void multiplayer()
{
	int scorX = 0, scor0 = 0, nrJocuri = 0;
	char primul, play = '1';
	do {
		cout << "Alegeti cine incepe jocul: " << endl;
		cout << "Apasati 1 pentru " << nume1 << " [X]" << endl;
		cout << "Apasati 2 pentru " << nume2 << " [O]" << endl;
		primul = _getche();
		while (primul != '1'&&primul != '2')
		{
			cout << "Optiune incorecta, incercati din nou: ";
			primul = _getche();
			system("CLS");
			cout << "Alegeti cine incepe jocul: " << endl;
			cout << "Apasati 1 pentru " << nume1 << " [X]" << endl;
			cout << "Apasati 2 pentru " << nume2 << " [O]" << endl;

		}
		if (primul == '1')
			jucator = 'X';
		else if (primul == '2')
			jucator = 'O';
		while (testCastig() != 'X'&&testCastig() != 'O')
		{
			system("CLS");
			masaJoc(matPoz);
			alegere();
			if (tablaPlina())
				break;
			schimbareJucator();
		}
		if (testCastig() == 'X')
		{
			scorX++;
			nrJocuri++;
			cout << "\n| ***" << nume1 << " a castigat!*** |" << endl;
			cout << "-------------------------------------------------" << endl;
		}
		else if (testCastig() == 'O')
		{
			scor0++;
			nrJocuri++;
			cout << "\n| ***" << nume2 << " a castigat!*** |" << endl;
			cout << "-------------------------------------------------" << endl;
		}
		else if (tablaPlina())
		{
			nrJocuri++;
			cout << "\n---------------" << endl;
			cout << "| ***Remiza!*** |" << endl;
			cout << "-----------------" << endl;
			masaJoc(matPoz);
		}
		scor(scorX, scor0, nrJocuri, nume1, nume2);
		cout << "-------------------------------------------------" << endl;
		cout << "| Apasati 1 pentru a juca din nou               |" << endl;
		cout << "| Apasati 2 pentru a reveni la meniul principal |" << endl;
		cout << "| Apasati 3 pentru a iesi                       |" << endl;
		cout << "-------------------------------------------------" << endl;
	eticheta:
		play = _getche();
		if (play == '1')
		{
			reset();
			system("CLS");
		}
		else if (play == '2')
		{
			joc = 2;
			reset();
			system("CLS");
			meniu();
		}
		else if (play == '3')
			exit(0);
		else
		{
			system("CLS");
			cout << "-------------------------------------------------" << endl;
			cout << "| Apasati 1 pentru a juca din nou               |" << endl;
			cout << "| Apasati 2 pentru a reveni la meniul principal |" << endl;
			cout << "| Apasati 3 pentru a iesi                       |" << endl;
			cout << "-------------------------------------------------" << endl;
			cout << "Optiune incorecta, incercati din nou: " << endl;
			goto eticheta;
		}
	} while (play == '1');
	system("CLS");
}

int main()
{
	int x;
	system("color 9A");
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
			cout << "\n| Easy(1) |";
			cout << "\n| Hard(2) |"<<endl;
			if (_getch() == '1')
			{
				fflush(stdin);
				singlePlayerEasy();
			}
			else if (_getch() == '2')
			{
				fflush(stdin);
				singlePlayerHard();
			}
			else
				cout << "Optiune incorecta";
			fflush(stdin);
			masaJoc(matPoz);

			cin >> x;
		case '2':
			while (joc == 2)
			{
				system("CLS");
				cout << "\nNumele primului jucator: ";
				cin >> nume1;
				cout << "Numele celui de-al doilea jucator: ";
				cin >> nume2;
				multiplayer();
				cin >> x;
			}
		case'3':
			system("CLS");
			cout << " X si 0, este un joc pentru doi jucatori, X respectiv 0 care marcheaza pe rand cate o casuta dintr-un tabel cu 3 linii si 3 coloane.\n";
			cout << "Jucatorul care reuseste sa marcheze primul 3 casute adiacente pe orizontala, verticala sau diagonala, castiga jocul."<<endl;
			cout << "\nExemplu:\n";
			masaJoc(exemplu);
			cout << "-------------------------------\n";
			cout << "Apasati 1 pentru a va intoarce la meniul principal\n";
			while (_getch() != '1')
			{
				system("CLS");
				cout << "Optiune incorecta, incercati din nou: ";
				_getch();
			}
			system("CLS");
			meniu();
			cin >> x;
		case '4':
			exit(0);
		default:
			cout << "\nOptiune incorecta!\n";
		}
		_getch();
	}
	cin >> x;

	return 0;
}
