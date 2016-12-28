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
	meniu();
	return 0;
}
