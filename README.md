#include"stdafx.h"
#include <iostream>
#include <conio.h>

using namespace std;

class cars
{
public:
	virtual void out() = 0;
	virtual void get() = 0;


	double weight;
	int seats;




	void basicInfo()
	{
		cout << "- вага: " << weight << endl;
		cout << "- кiлькiсть мiсць: " << seats << endl;
	}










};




class car : public cars
{
public:
		int price;


		void get() {
			cout << "Вага: ";
			cin >> weight;
			cout << "Кiлькiсть мiсць: ";
			cin >> seats;
			cout << "Цiна: ";
			cin >> price;


	}
};


class gromTransp : public cars
{
public:
	int power;


	void get() {
		cout << "Вага: ";
		cin >> weight;
		cout << "Кiлькiсть мiсць: ";
		cin >> seats;
		cout << "Кіньські сили: ";
		cin >> power;


	}
};


class vantagn : public car
{
public:
	void out()
	{
		cout << "- цiна: " << price;
	}
};


class zvuchayna : public car
{
public:
	void out()
	{
		cout << "- цiна: " << price;
	}
};


class lehkova : public car
{
public:
	void out()
	{
		cout << "- цiна: " << price;
	}
};




class bas : public gromTransp

{
public:
	void out()
	{
		cout << "- потужність: " << power;
	}


};


class tramv : public gromTransp

{
public:
	void out()
	{
		cout << "- потужність: " << power;
	}


};


class troleyb : public gromTransp

{
public:
	void out()
	{
		cout << "- потужність: " << power;
	}


};

int main()
{
	int S;
	setlocale(LC_ALL, "Russian");


	cars *mas[10];


	mas[1] = new vantagn;
	mas[2] = new zvuchayna;
	mas[3] = new lehkova;
	mas[4] = new bas;
	mas[5] = new tramv;
	mas[6] = new troleyb;

	cout << "Машини: \n";
	cout << "1. Вантажний автомобіль\n";
	cout << "2. Автомобіль\n";
	cout << "3. Легковий автомобіль\n";
	cout << "4. Автобус\n";
	cout << "5. Трамвай\n";
	cout << "6. Тролейбус\n";

	cout << endl;
	cin >> S;
	cout << endl;


	mas[S]->get();
	cout << endl;


	mas[S]->basicInfo();
	mas[S]->out();
	_getch();
	return 0;
}
