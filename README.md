# Cash-Register
Takes ticket information for children and adults and calculates there bill.

// Author:			Keith Holler
// Source file:		TheShape.cpp
// Description:		Select a shape then enter a width if the width is even it will ask to put an odd width.
// IDE used:	    Visual C++ 2010 Express
// Date:			10/06/2014

#include <iostream>
#include <iomanip>
#include <math.h>
#include<cmath>
using namespace std;
void displayMenu(int&);
void getData(int&);
void displaySquare(int&);
void displayUpSideDownTriangle(int&);
void displayTriangle(int&);
void displayDiamond(int&);

int main ()
{	int number, width;
	do
	{
		displayMenu(number);
	
	if (number == -9)
		{
			return 0;
		}

	else
		{
			getData(width);
			cout<<"\n";
		}

	switch(number)
	{
	case 1: displaySquare(width);
		break;
	case 2: displayTriangle(width);
		break;
	case 3: displayUpSideDownTriangle(width);
		break;
	case 4: displayDiamond(width);
		break;
	default: cout << " Not a valid number!";
		break;
	}

	cout<<"\n";
	}

	while(number!= -9);
}

void  displayMenu(int& number)
{
	cout<<"   Shape Display Menu\n\n";
	cout<<"     1....Square\n";
	cout<<"     2....Triangle\n";
	cout<<"     3....Upside Down Triangle\n";
	cout<<"     4....Diamond\n\n";
	cout<<"    -9....Exit Program";
	cout<< "\n\n Make a selection....";
	cin>>number;
}

void getData(int& width)
{ 
	cout<< " Enter width of shape... ";
	cin>>width;
	
while(width%2 == 0)
	{
		cout<< " Please enter a odd number";
		cout<< " \n\n Enter width of shape... ";
		cin>>width;
	}
}

void displaySquare(int& width)
{
	double	height;

	for (int i=0; i<width;i++)
		{
			for(int j=0; j<width; j++)
			{
				cout<< "#";
			}
		cout<<endl;
	}
}
	  
void displayUpSideDownTriangle(int& width)
{   
	double	height;
	height = width/2;
	height = ceil(height);

	 for (int i=0; i<=height;i++)
		{
			for(int j=0; j<i; j++)
				{
					cout<<" ";
				}

		for(int k=0; k<width; k++)
			{
				cout<<"#";
			}
			
			width = width -2;

			cout<< endl;
	 }
}

			
void displayTriangle(int& width)
{
	double	height;

	height = width/2;

	height = ceil(height);


	  for (int i=0; i<=height;i++)
		{
			for(int j=height; j>i; j--)
		{
			cout<<" ";	
		}

		for(int k=1; k<=2*i+1; k++)
			{
				cout<<"#";
			}
		
			cout<< endl;
	  }
}

void displayDiamond(int& width)
{
	displayTriangle(width);

	displayUpSideDownTriangle(width);
}
