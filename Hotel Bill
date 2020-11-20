/*
name: Khaled Ahmed
Date: 04/20/2020
Project Name: PCCC Selection Hotel
Description: This program takes the input from a customer by asking for their name, what room number they stayed in and how many days they stayed for to determine their total bill for staying at the hotel.

*/
#include <iostream>
#include <string>
#include <fstream>
#include <iomanip>

using namespace std;

// all prototypes for the function calls
void setinfo(string &, int &, int &);
float setroom(int, int, string &, float);
float setnet(int,string &);
float settv(int,string&);
void getinfo(string, int, float, float, float, string, string, string, float, float, float, ofstream&);

int main()
{  

	ofstream fout ("HOTEL.out"); 	// sending to file called HOTEL
    
    // all the variables used in main
	string name;
    string roomtype;
    string nettype;
    string tvtype;
	int days;
	int roomnumber;
    float roomcharges;
	float netcharges;
	float tvcharges;
	float roomcost;
	float totalcharges;
	float localtaxes;
	float totaldue;
    
    // all functions that provide information
	
	setinfo(name,roomnumber,days); // function call for name, roomnumber and days
    roomcharges = setroom(roomnumber, days,roomtype,roomcost); // function call for room charges
    netcharges =  setnet(days,nettype); // function call for internet charges
    tvcharges = settv(days,tvtype); // function call for television charges
    getinfo(name, days,roomcharges,netcharges,tvcharges,roomtype,nettype,tvtype,totalcharges,localtaxes,totaldue, fout);  // function call for all of the output
    
    // proccessing 
    cout << fixed<<showpoint<<setprecision(2);    // all monies set to 2 decimal places
   
   	const float LOCAL_TAXES = .15;  // constant for local tax
    totalcharges = roomcharges + netcharges + tvcharges;  // total charges for hotel stay
    localtaxes = totalcharges * LOCAL_TAXES;   //taxes for the total bill
    totaldue = totalcharges + localtaxes;  // total bill due after taxes
  
    return 0;
}

// function definitions for all the functions in main

void setinfo(string &name, int &roomnumber, int &days)  
{
	system("CLS"); // clears the screen to display these inputs
	cout << "Name please: "; getline (cin, name);
	
	
	cout << "Room number: "; cin >> roomnumber;

	
	cout << "How many days are you staying for: "; cin >> days;
	
}

float setroom(int roomnumber, int days, string &roomtype, float roomcost)
{
	const float SINGLE_ROOM = 99.99;
	const float FAMILY_ROOM = 149.99;
	const float SUITE_ROOM = 199.99;
	if (roomnumber <=19)
		roomtype = "Single Room";
	else
		if (roomnumber <=39)
			roomtype = "Family Room";
		else 
			if (roomnumber <=50)
				roomtype = "Suite";

	if (roomnumber <=19)
		roomcost = SINGLE_ROOM;
	else
		if (roomnumber <=39)
			roomcost = FAMILY_ROOM;
		else 
			if (roomnumber <=50)
				roomcost = SUITE_ROOM;
	
	return roomcost * days;
}
float setnet(int days, string &nettype)
{
	system("CLS");  // clears the screen to display these inputs
	const float WIRELESS = 5.95;
	const float WIRED = 3.95;
	char choice1;
	float netcost = 0;
	char netselection;
	
	cout << "Are you using internet?: Enter choice Y or N" << endl; cin >> netselection;
	
	if (netselection == 'Y' || netselection == 'y')
		{
			cout << "Internet type:" << endl;
			cout << "1 - Wired" << endl; 
        	cout << "2 - Not-wired (Wireless)" << endl;
        	cout << "Enter Choice 1 or 2: " << endl; cin >> choice1;
        	nettype = choice1;
  	    }
	else 
		if (netselection == 'N'|| netselection == 'n')
    		{
				nettype = "(none)";
			    netcost = 0;
			}
    	
   
    if (choice1 == '1' || choice1 == 'W' || choice1 == 'w')
    	{
			nettype = "(Wired)";
    		netcost = WIRED;
		}
    else
		if (choice1 == '2' || choice1 == 'N' || choice1 == 'n')
    		{
				nettype = "(Wireless)";
    			netcost = WIRELESS;
    		}
    return days * netcost;
    

}
float settv(int days, string &tvtype)
{
	system("CLS");  // clears the screen to display these inputs
	float CABLE_CHANNELS = 4.95;
	float BASIC_CHANNELS = 1.95;
	char choice2;
	float tvcost;
	char tvselection;
	
	cout << "Are you using television?: Enter choice Y or N" << endl; cin >> tvselection;
	
	if (tvselection == 'Y' || tvselection == 'y')
		{
			cout << "Television Types:" << endl;
			cout << "1 - Cable Channels" << endl; 
        	cout << "2 – Basic Channels" << endl;
        	cout << "Enter Choice 1 or 2: " << endl; cin >> choice2;
        	tvtype = choice2;
        } 	
	else
	    if (tvselection == 'N'|| tvselection == 'n')
    		{
				tvtype = "(none)";
				tvcost = 0;
			}
			

    	
    if (choice2 == '1' || choice2 == 'C' || choice2 == 'c')
    	{
    		tvtype = "(Cable)";
    		tvcost = CABLE_CHANNELS;
		}
    	
    else 
		if (choice2 == '2' || choice2 == 'B' || choice2 == 'b')
    		{		
				tvtype = "(Basic)";
    			tvcost = BASIC_CHANNELS;
			}
	return days * tvcost;
}
void getinfo(string name, int days, float roomcharges, float netcharges, float tvcharges, string roomtype, string nettype, string tvtype, float totalcharges, float totaltaxes, float totaldue, ofstream &fileout)
{
	fileout << "\t\tPCCC Palace Hotel" << endl;
	fileout << name << "'s Billing Statement" << endl;
	fileout << "\nNumber of days in hotel: " << days << " in a " << roomtype << endl;
	fileout << "\n\tRoom charges: " << "$" << roomcharges << endl;
	fileout << "\tInternet charges: " << nettype << "\t$" << netcharges << endl;
	fileout << "\tTelevision charges: " << tvtype << "\t$" <<tvcharges << endl;
	fileout << "\n\tTotal charges: " << "$"  << totalcharges << endl;
	fileout << "\n\tTotal taxes: " << "$"  << totaltaxes << endl;
	fileout << "\n\tTotal due: " << "$" << totaldue << endl;
	fileout << "\nThank you for using PCCC Palace Hotel. Hope to see you again." << endl;
}

