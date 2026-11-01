# Admin user ID and Password
ID = "xyz"
Password = "123"

# Details of Employee
Employee_ID = []
name = []
age = []
gender = []
depertment = []
salary = []

# Salary Structure for the employees
Basic_Salary = []
Bonus = []
Deduction = []


def log_in():

    User_ID = input("Enter your User ID: ")
    passcode = input("Enter your Password: ")

    if User_ID == ID and Password == passcode:

        while True:

            print("------------------------")
            print("      WelCOme Sir       ")
            print("------------------------")

            print("------- Main Menu -------")
            print("1. Add Employee")
            print("2. Remove Employee")
            print("3. View Employee")
            print("4. View all Employees")
            print("5. Log Out")
            print("-------------------------")

            choice = int(input("Enter What Change you want to make: "))

            if choice == 1:

                employee_id = input("Enter Employee ID: ")

                if employee_id in Employee_ID:
                    print("Employee ID already exists!")
                    continue

                Name_of_employee = input("Enter name of employee: ")
                Age_of_employee = int(input("Enter age of the employee: "))
                Gender_of_employee = input(
                    "Enter Gender of employee(M / F / O): "
                ).upper()

                Depentment_of_employee = input(
                    "Enter Department of the employee: "
                )

                salary_of_employee = float(
                    input("Enter Salary of the Employee: ₹")
                )

                bonus_of_employee = float(
                    input("Enter Bonus of the Employee: ₹")
                )

                deduction_of_employee = float(
                    input("Enter Deduction of the Employee: ₹")
                )

                if Age_of_employee < 18:

                    print("Employee Cannot work")
                    print("Due to under age!")

                else:

                    Employee_ID.append(employee_id)
                    name.append(Name_of_employee)
                    age.append(Age_of_employee)
                    gender.append(Gender_of_employee)
                    depertment.append(Depentment_of_employee)
                    salary.append(salary_of_employee)

                    Basic_Salary.append(salary_of_employee)
                    Bonus.append(bonus_of_employee)
                    Deduction.append(deduction_of_employee)

                    print("Employee Is ready to Work")

                print("-------------------------")

            elif choice == 2:

                employee_id = input(
                    "Enter Employee ID you want to remove: "
                )

                if employee_id in Employee_ID:

                    index = Employee_ID.index(employee_id)

                    Employee_ID.pop(index)
                    name.pop(index)
                    age.pop(index)
                    gender.pop(index)
                    depertment.pop(index)
                    salary.pop(index)

                    Basic_Salary.pop(index)
                    Bonus.pop(index)
                    Deduction.pop(index)

                    print("Employee removed successfully!")

                else:

                    print("Employee not found!")

            elif choice == 3:

                employee_id = input("Enter Employee ID: ")

                if employee_id in Employee_ID:

                    index = Employee_ID.index(employee_id)

                    print("--------------------------------")
                    print("Employee ID:", Employee_ID[index])
                    print("Name:", name[index])
                    print("Age:", age[index])
                    print("Gender:", gender[index])
                    print("Department:", depertment[index])
                    print("Salary:", salary[index])
                    print("--------------------------------")

                else:

                    print("Employee Not Found!")

            elif choice == 4:

                if len(Employee_ID) == 0:

                    print("No Employee Found!")

                else:

                    for i in range(len(Employee_ID)):

                        print("--------------------------------")
                        print("Employee ID:", Employee_ID[i])
                        print("Name:", name[i])
                        print("Age:", age[i])
                        print("Gender:", gender[i])
                        print("Department:", depertment[i])
                        print("Salary:", salary[i])
                        print("--------------------------------")

            elif choice == 5:

                print("LOGGED OUT")
                print("Thank YOU SIR!")
                break

            else:

                print("Invalid Choice!")
                print("Try Again!")

    else:

        print("Invalid User ID or Password!")


# Salary Management

def salary():

    while True:

        print("=================================")
        print("   Welcome to Salary Management  ")
        print("=================================")

        print("1. Salary of Individual Employee")
        print("2. Salary of all Employees")
        print("3. Log Out")

        print("-----------------------------------")

        choice = int(input("Enter your Choice: "))

        if choice == 1:

            employee_id = input("Enter Employee Id: ")

            if employee_id in Employee_ID:

                index = Employee_ID.index(employee_id)

                basic = Basic_Salary[index]
                bonus = Bonus[index]
                deduction = Deduction[index]

                hra = basic * 0.20
                da = basic * 0.10

                gross_salary = basic + hra + da + bonus
                net_salary = gross_salary - deduction

                print("\n------ SALARY DETAILS ------")
                print("Employee ID   :", Employee_ID[index])
                print("Employee Name :", name[index])
                print("Basic Salary  :", basic)
                print("HRA           :", hra)
                print("DA            :", da)
                print("Bonus         :", bonus)
                print("Deduction     :", deduction)
                print("Gross Salary  :", gross_salary)
                print("Net Salary    :", net_salary)

            else:

                print("Employee Not Found!")

        elif choice == 2:

            if len(Employee_ID) == 0:

                print("No Employee Found!")

            else:

                for i in range(len(Employee_ID)):

                    basic = Basic_Salary[i]
                    bonus = Bonus[i]
                    deduction = Deduction[i]

                    hra = basic * 0.20
                    da = basic * 0.10

                    gross_salary = basic + hra + da + bonus
                    net_salary = gross_salary - deduction

                    print("\n-----------------------------")
                    print("Employee ID   :", Employee_ID[i])
                    print("Employee Name :", name[i])
                    print("Basic Salary  :", basic)
                    print("HRA            :", hra)
                    print("DA             :", da)
                    print("Bonus          :", bonus)
                    print("Deduction      :", deduction)
                    print("Gross Salary   :", gross_salary)
                    print("Net Salary     :", net_salary)
                    print("-----------------------------")

        elif choice == 3:

            print("Logged Out!")
            print("Thank You")
            break

        else:

            print("Invalid Choice!")
            print("Try Again!")


# Main Program

while True:

    print("------------------------------")
    print("     Wel Come xyz Company     ")
    print("------------------------------")

    print("========= Main Menu ==========")

    print("1. Log In")
    print("2. Salary Management")
    print("3. Log Out")

    choice = int(input("Enter Your Choice: "))

    if choice == 1:

        log_in()

    elif choice == 2:

        salary()

    elif choice == 3:

        print("Logged Out!")
        print("Thank You")
        break

    else:

        print("Invalid Choice!")
        print("Try Again!")
