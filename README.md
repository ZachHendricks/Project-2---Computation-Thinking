# Project-2---Computation-Thinking

Zach Hendricks, Carter Barnes, Elise Rodriguez

import os

os.mkdir('Assignment2')

#set a breaking variable 
typeStud = []
loan = []
subRate = []
unsubRate = []

years = 0

current_student = True #Statement to break the loop 

#Get the inputs
while current_student == True:
    years += 1  
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
            if years == 1 and Studenttype == "I" and loanamt <=9500 or years == 1 and Studenttype == "D" and loanamt <= 5500:
                loan.append(loanamt)
                break
            elif years == 2 and Studenttype == "I" and loanamt <=10500 or years == 2 and Studenttype == "D" and loanamt <= 6500:
                loan.append(loanamt)
                break
            elif years > 2 and Studenttype == "I" and loanamt <=12500 or years > 2 and Studenttype == "D" and loanamt <= 7500:
                loan.append(loanamt)
                break
            else:
                print("Error: Please enter valid loan amount. See studentaid.gov to verify loan amount.")
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
