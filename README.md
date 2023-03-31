# Project-2---Computation-Thinking

#set a breaking variable 
typeStud = []
loan = []
subRate = []
unsubRate = []

years = 0

current_student = True #Statement to break the loop 

#Get the inputs
while current_student == True:
    
    try:    
        Studenttype = input("Enter I for Independend or D for Dependent Student for this school year: ")
        if Studenttype == "I" or Studenttype == "D":
            typeStud.append(Studenttype)
        else:
            print("Error: Invalid input. Please enter 'I' or 'D'")
            continue #continue loops back to the first input statement to try again
    except:
        print("Error: Invalid input. Please enter 'I' or 'D' ")
        
#Get the second input
    while True: #loop to enter the loan amount/print error
        try:
            loanamt = int(input("What is the total loan amount for this school year: "))
            if loanamt <= 12500:
                loan.append(loanamt)
                break
            else:
                print("Error: Please enter valid loan amount")
                continue
        except:
            print("Error: Please enter valid loan amount")

#Third input
    while True:
        try:
            subrate = float(input("What is the subsidized loan interest rate: "))
            subRate.append(subrate)
            break
        except:
            print("Error: Please enter a number")

#Fourth input
    while True:
        try:
            unsubrate = float(input("What is the unsubsidized loan interest rate: "))
            unsubRate.append(unsubrate)
            break
        except: 
            print("Error: Please enter a number")
            continue

#last input/break the loop
    while True:
        try:
            Anotheryear = input("Are you attending another year of undergraduate college 'Y' or 'N': ")
            if Anotheryear == "Y":
                break
            elif Anotheryear == "N":
                current_student = False #if not another year, break the first loop
                break
            else:
                print("Error: Invalid input. Please enter 'Y' or 'N'")
                continue
        except:
            print("Error: Invalid input. Please enter 'Y' or 'N'")
    
    
#add a year to the count
    years += 1

#Part B

subLoanLimit = [3500,4500,5500]
indepLoanLimit = [9500,10500,12500]
depLoanLimit = [5500,6500,7500]
Total = 0

for academic_year in range(years):
    if academic_year < 2:
        ind = academic_year
    else:
        ind = min(2, academic_year)
        
    #Unsub loan amount
    UnsubsidizedAmt = loan[academic_year] - subLoanLimit[ind]
    #interest
    An_unsub = unsubRate[academic_year]
    Mon_unsub= An_unsub / 12 / 100
    
    months = (years - academic_year)* 12 + 3
    
    for i in range(months):
        UnsubsidizedAmt *= (1 + Mon_unsub)
        
    Total = Total + UnsubsidizedAmt + subLoanLimit[ind]
