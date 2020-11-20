'''
    Name: Khaled Ahmed
    Class: CIS 108 M01
    Date: 11/20/2019
    Program Name: The Passaic County Catering and Convention 
    Description: This program generates a customer's total cost of catering by figuring out how      many adults and children are attending, then taking that information to figure out how much the total is with a deposit in the beginning, food cost, weekend surcharge (if its on a weekend), the cost of the hall, discount depending on total price, and then ends with adding the total with tax rate. 
    
'''



#imports
from random import randint

#constants
DELUXE_MEAL = 25.95
STANDARD_MEAL = 21.75
HALL_A = 1000.00
HALL_B = 850.00
HALL_C = 750.00
HALL_H = 0.00
SURCHARGE = 0.10
DISCOUNT_1 = 0.02
DISCOUNT_2 = 0.04
DISCOUNT_3 = 0.05
DISCOUNT_4 = 0.07
CHILD_MEAL_COST = 0.50 #50% of adult meals
GRATUITY = 0.20
TAX_RATE = 0.068




def main():

    #input ( all the information needed for evaluation )
    adults = int(input("How many adults are attending?: "))
    children = int(input("How many children are attending?: "))
    deposit = float(input("How much are you depositing?: "))
    weekend = input("Is this catering on a weekend? Yes-No: ")
    hall = input("Which hall are you choosing? A-B-C-H: ")
    typemeal = input("Which type of meal? Standard-Deluxe: ").upper()[0]
    
    
    
    
    #processing ( finding out the total cost for everything )
    invoice = randint(100,999)

    if (typemeal == 'Standard' or typemeal == 'S'):
        mealname = 'Standard'
        costpsma = STANDARD_MEAL                      #cost per standard meal for adult
        costpsmc = float(costpsma * CHILD_MEAL_COST)  #cost per standard meal for child
    elif (typemeal == 'Deluxe' or typemeal == 'D'):
        mealname = 'Deluxe'
        costpdma = DELUXE_MEAL                        #cost per deluxe meal for adult
        costpdmc = float(costpdma * CHILD_MEAL_COST)  #cost per deluxe meal for child
    else:
        print("Please pick a choice, Standard or Deluxe")

    if (typemeal == 'Standard' or typemeal == 'S'):
        meal1 = STANDARD_MEAL
        meal2 = float(STANDARD_MEAL * CHILD_MEAL_COST)
    elif (typemeal == 'Deluxe' or typemeal == 'D'):
        meal1 = DELUXE_MEAL
        meal2 = float(DELUXE_MEAL * CHILD_MEAL_COST)

    

    #total cost for types of meal
    if (typemeal == 'Standard' or typemeal == 'S'):
        totalcostadult = costpsma * adults
        totalcostchild = costpsmc * children
    elif (typemeal == 'Deluxe' or typemeal == 'D'):
        totalcostadult = costpdma * adults
        totalcostchild = costpdmc * children
   

    #total food cost including adults and children
    totalfoodcost = totalcostadult + totalcostchild

    #gratuity fee
    gratuity2 = totalfoodcost * GRATUITY

    #room fee
    if (hall == 'A' or hall == 'a'):
        roomfee = HALL_A
    elif (hall == 'B' or hall == 'b'):
        roomfee = HALL_B
    elif (hall == 'C' or hall == 'c'):
        roomfee = HALL_C
    elif (hall == 'H' or hall == 'h'):
        roomfee = HALL_H


    #weekend charge
    if (weekend == 'Yes' or weekend == 'Y'):
        weekend = 'Yes'
        weekendcharge = float(totalfoodcost * SURCHARGE)
    elif (weekend == 'No' or weekend == 'N'):
        weekend = 'No'
        weekendcharge = 0

        
    totalcostbeforetaxes = float(totalfoodcost + roomfee + weekendcharge) #total cost before taxes excluding gratuity
    taxes = float(totalcostbeforetaxes * TAX_RATE)
    subtotal = float(totalfoodcost + gratuity2 + roomfee + weekendcharge + taxes)

    #Less Speedy Payment
    if (subtotal <= 1000):
        lsp = subtotal * DISCOUNT_1
    elif (subtotal <= 2000):
        lsp = subtotal * DISCOUNT_2
    elif (subtotal <= 5000):
        lsp = subtotal * DISCOUNT_3
    elif (subtotal >= 5000):
        lsp = subtotal * DISCOUNT_4
    else:
        lsp = 0


    balancedue = subtotal - deposit - lsp
    
   #output ( introducing and giving the results of everything )
    print("/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/")
    print("\tCaswell Catering and Convention Services")
    print("\t\tFinal Bill", "\tInvoice#", invoice)
   

    print("/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/")

    print("\nNumber of adult: ", adults)
    print("Number of children: ", children)
    print("Gratuity: 20%")
    print("Weekend:",weekend)
    print("Cost per ", mealname, " meal for adult: ", "\t" "$",format(meal1,'.2f'),sep="")
    print("Cost per ", mealname, " meal for child: ", "\t" "$",format(meal2,'.2f'),sep="")

    print("\n--------------------------------------------------")

    print("\nTotal cost for adult meals: ", "\t\t" "$",format(totalcostadult,'.2f'),sep="")
    print("Total cost for child meals: ", "\t\t" "$",format(totalcostchild,'.2f'),sep="")
    print("\nTotal food cost: ", "\t\t\t" "$",format(totalfoodcost,'.2f'),sep="")

    print("\n--------------------------------------------------")

    print("\nGratuity: ", "\t\t\t\t" "$",format(gratuity2,'.2f'),sep="")
    print("Hall ",hall,"- Room fee: ", "\t\t\t" "$",format(roomfee,'.2f'),sep="")
    print("Weekend charge: ", "\t\t\t" "$",format(weekendcharge,'.2f'),sep="")
    print("Taxes: ", "\t\t\t\t\t" "$",format(taxes,'.2f'),sep="")
    
    print("\n--------------------------------------------------")

    print("\nSubtotal: ", "\t\t\t\t" "$", format(subtotal,'.2f'),sep="")
    print("\nLess deposit: ", "\t\t\t\t" "$",format(deposit,'.2f'),sep="")
    print("Less Speedy Payment: ", "\t\t\t" "$",format(lsp,'.2f'),sep="")
    print("\n\nBalance Due: ", "\t\t\t\t" "$",format(balancedue,'.2f'),sep="")

    print("\n/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/")

    print("\tThank you for using Caswell Catering") 
    
    

main()
input("Press Enter to continue")
