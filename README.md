# Project-2---Computation-Thinking

#Zach Hendricks, Carter Barnes, Elise Rodriguez

#set a breaking variable 
typeStud = []
loan = []
subRate = []
unsubRate = []

years = 0

current_student = True

#Get the inputs
while current_student == True:
    
    try:    
        Studenttype = input("Enter I for Independend or D for Dependent Student for this school year: ")
        if Studenttype == "I" or Studenttype == "D":
            typeStud.append(Studenttype)
        else:
            print("Error: Invalid input. Please enter 'I' or 'D'")
            continue
    except:
        print("Error: Invalid input. Please enter 'I' or 'D' ")
        
#Get the second input
    while True:
        try:
            loanamt = int(input("What is the total loan amount for this school year: "))
            if loanamt <= 12500:
                loan.append(loanamt)
                break
            else:
                print("Error: Loan amount must be less than $12,500")
                continue
        except:
            print("Error: Loan amount must be less than $12,500")

#Third input
    while True:
        try:
            subrate = int(input("What is the subsidized loan interest rate: "))
            subRate.append(subrate)
            break
        except:
            print("Interest rate must be an integer")

#Fourth input
    while True:
        try:
            unsubrate = int(input("What is the unsubsidized loan interest rate: "))
            unsubRate.append(unsubrate)
            break
        except: 
            print("Interest rate must be an integer")
            continue

#last input/break the loop
    while True:
        try:
            Anotheryear = input("Are you attending another year of undergraduate college 'Y' or 'N': ")
            if Anotheryear == "Y":
                break
            elif Anotheryear == "N":
                current_student = False
                break
            else:
                print("Error: Invalid input. Please enter 'Y' or 'N'")
                continue
        except:
            print("Error: Invalid input. Please enter 'Y' or 'N'")
    
    
#add a year to the count
    years += 1
