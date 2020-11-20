/*
name: Khaled Ahmed
Date: 02/22/2020
project Name: Caswell Catering Project
description: this program takes the input from a customer of how many adults and 
children are attending and how many pieces of dessert they are getting to figure 
out their total bill including an 18% tip amount from the total cost of the food. 


*/
#include <iostream>
#include <string>
#include <iomanip>
using namespace std;
const float CHILD_COST = 0.50;
const float DESSERT_COST = 5.50;
const float TAX_RATE = 0.06825;
const float GRATUITY = 0.18;

int main()
{

	// input section
	// all the variables needed for input and processing
	string customerName;
	int adults;
	int children;
	int dessertAmount;
	float costPerAdult;
	float roomFee;
	float lessDeposit;
	float costPerChild;
	float totalAdultCost;
	float totalChildCost;
	float totalDessertCost;
	float totalFoodCost;
	float tipAmount;
	float taxes;
	float totalBill;
	float balanceDue;
	
cout << "Enter your name: ";      // asks customer for their name
	getline(cin, customerName);
 
	cout << "How many adults?: ";     // asks how many adults are attending
	cin >> adults;

	cout << "How many children?: ";   // asks how many children are attending
	cin >> children;

	cout << "What is the cost per adult?: ";   // asks for input of how much the cost per adult 
is
	cin >> costPerAdult;


	cout << "How many dessert pieces?: ";    // asks how many dessert pieces customer is 
buying
	cin >> dessertAmount;
	
	cout << "How much deposit are you making?: ";   // asks the customers how much they 
are depositing upfront
	cin >> lessDeposit;
	


	// processing section
	
	cout << fixed<<showpoint<<setprecision(2);    // all monies set to 2 decimal places
	
	costPerChild = costPerAdult * CHILD_COST;    // half the cost of adult meal

	totalAdultCost = adults * costPerAdult;      // total cost of food for adults
	totalChildCost = children * costPerChild;    // total cost of food for children
	totalDessertCost = dessertAmount * DESSERT_COST;    // total cost for desserts
	totalFoodCost = totalAdultCost + totalChildCost + totalDessertCost;    // total cost for all 
the food 
	roomFee = 0;
	tipAmount = totalFoodCost * GRATUITY;    // the amount of tip required 
	taxes = totalFoodCost * TAX_RATE;     // tax rate taken from total food cost
	totalBill = totalFoodCost + taxes + tipAmount;    // all the cost including food, taxes and
	tips
	balanceDue = totalBill - lessDeposit;     // how much the customer owes 

	// output section
	
	
// displaying the total bill with each section that includes every amount 
	
	cout << "Passaic County Catering & Convention Services     Final Bill" << endl;

	cout << "Customer: " << customerName << endl;
	cout << "Number of adults: " << adults << endl;
	cout << "Number of children: " << children << endl;

	cout << "Cost of Meal Per Adult: $" << costPerAdult << endl;
	cout << "Cost of Meal per Child: $" << costPerChild << endl;
	cout << "Cost per Dessert: $" << DESSERT_COST << endl;
	cout << "Total Food Cost: $" << totalFoodCost << endl;

	cout << "Plus 6.825% taxes: $" << taxes << endl;
	cout << "Plus 18.00% Tips: $" << tipAmount << endl;
	cout << "Plus Room Fee: $" << roomFee << endl;

	cout << "Total Bill: $" << totalBill << endl;
	cout << "Less Deposit: $" << lessDeposit << endl;

	cout << "Balance Due: $" << balanceDue << endl;


	cout << "Thank you for using Passaic County Catering Services." << endl;



	return 0;
}


