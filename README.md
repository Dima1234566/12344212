#include"stdafx.h"
#include <iostream>
#include <conio.h>

using namespace std;

class cars // маємо клас машини
{
public:
	virtual void out() = 0;
	virtual void get() = 0;


	double weight;
	int seats;




	void basicInfo()   // вводим що вони мають і що наступні об*єкти унаслідують
	{
		cout << ".....вага: " << weight << endl; 
		cout << ".....кiлькiсть мiсць: " << seats << endl;
	}










};




class car : public cars   // дочірній клас машина
{
public:
		int price;


		void get() {
			cout << ".....Вага: ";
			cin >> weight;
			cout << ".....Кiлькiсть мiсць: ";
			cin >> seats;
			cout << ".....Цiна: ";
			cin >> price;


	}
};


class Public transport : public cars  // дочірній клас громадський транспорт
{
public:
	int power;


	void get() {
		cout << ".....Вага: ";
		cin >> weight;
		cout << ".....Кiлькiсть мiсць: ";
		cin >> seats;
		cout << ".....Кіньські сили: ";
		cin >> power;


	}
};


class cargo : public car   // дочірній клас має підкласи..
{
public:
	void out()
	{
		cout << "..... цiна: " << price;
	}
};


class Redwood : public car   //   які мають однакову..
{
public:
	void out()
	{
		cout << "..... цiна: " << price;
	}
};


class automobile : public car   //характеристику
{
public:
	void out()
	{
		cout << "..... цiна: " << price;
	}
};



// інший дочірній клас зі своїми підкласами
class bas : public Public transport   

{
public:
	void out()
	{
		cout << "..... потужність: " << power;
	}


};


class tram : public Public transport

{
public:
	void out()
	{
		cout << "..... потужність: " << power;
	}


};


class trolleybus : public Public transport

{
public:
	void out()
	{
		cout << "..... потужність: " << power;
	}


};
// далі вивід
int main()
{
	int S;
	setlocale(LC_ALL, "Russian");


	cars *ez[10];
 //шлях до підкласів класу

	ez[1] = new cargo;
	ez[2] = new Redwood;
	ez[3] = new automobile;
	ez[4] = new bas;
	ez[5] = new tram;
	ez[6] = new trolleybus;

	cout << " ...... Машини...... \n";
	cout << "1. Вантажний автомобіль\n";
	cout << "2. Автомобіль\n";
	cout << "3. Легковий автомобіль\n";
	cout << "4. Автобус\n";
	cout << "5. Трамвай\n";
	cout << "6. Тролейбус\n";

	cout << endl;
	cin >> S;
	cout << endl;

    // вибір об*єкта наслідування
	ez[S]->get();
	cout << endl;
 // вивід

	ez[S]->basicInfo();
	ez[S]->out();
	_getch();
	return 0;
}
