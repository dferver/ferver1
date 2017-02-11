# ferver1
// name: David Ferver
// date: 11 Feb 2017
// Program Name: Stockmarket Portfolio Tracker
// Description: The following is an agrivating code attempting to output the purchase and sales of a technical stock.

#include<iostream>
#include<string>
#include<cstdlib>
#include<ctime>
#include<iomanip>
using namespace std;

int main()
{
	string stock_name;
	string stock_symbol;

	int shares_purchased;
	int random_number; 	
 
	int flip; 
	int fluctuation;

	cout << "Enter stock name" << endl;
	getline (cin, stock_name);

	cout << "Enter stock symbol" << endl;
	getline (cin, stock_symbol);

	cout << "Enter number of shares purhcased" << endl;
	cin >> shares_purchased;

	double share_price; 
	cout << "Price per share" << endl;
	cin >> share_price;

	double commission_rate;
	cout << "Enter commission rate" << endl;
	cin >> commission_rate;

	double percent_change;
	unsigned seed = time(0);				// random number generator 
	srand(seed);							// used to simulate percentage change in sale price.
	random_number = rand() % 100;
	percent_change = random_number / 100;
	cout << percent_change << endl;
	cout << "percent_change =" << percent_change;

	double profit_loss;
	flip = rand() % 2 + 1;					// coin flip
	if (flip == 1) profit_loss = 1;			// used to show gain or loss 
	else profit_loss = -1;
	cout << "profit_loss =" << profit_loss << endl;

	double pos_neg_percent = percent_change * profit_loss;
	cout << "the percentage of profit loss is " << pos_neg_percent << "%." << endl;

	double share_cost = share_price * shares_purchased;
	double commission_paid = commission_rate * share_price;
	double purchase_cost = share_cost = commission_rate;

	double new_share_price = (pos_neg_percent * share_price) + share_price;
	cout << "New shares: " << new_share_price << endl;

	double new_share_value = new_share_price * shares_purchased;
	double stock_sales = commission_rate * new_share_price;
	double sale_net = share_price + commission_rate;

	cout << "The name of the stock is " << stock_name << endl;
	cout << "The stock symbol is " << stock_symbol << endl;
	cout << "The number of shares purchased is " << shares_purchased << endl;
	cout << "The price per share is " << share_price << endl;
	cout << "The commission rate for the stock is " << commission_rate << endl;
	cout << "The commission ammount is " << commission_paid << endl;
	cout << "The percent_change is " << percent_change << endl;



	system("pause");
	return 0;
}
