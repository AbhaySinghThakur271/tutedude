employees={101: {'name': 'Satya', 'age': 27, 'department': 'HR', 'salary': 50000},102: {'name': 'Raj', 'age': 24, 'department': 'IT', 'salary': 55000},103: {'name': 'Amit', 'age': 27, 'department': 'HR', 'salary': 52000},104: {'name': 'Urvashi', 'age': 22, 'department': 'IT', 'salary': 40000}}
def add_employee():
    try:
        emp_id=int(input("Enter employee ID -"))
        if emp_id in employees:
            print("Error: Employee ID already exists. Try again.\n")
        else:
            name = input("Enter Name: ")
            age = int(input("Enter Age: "))
            department = input("Enter Department: ")
            salary = float(input("Enter Salary: "))
            employees[emp_id] = {'name': name,'age': age,'department': department,'salary': salary}
    except ValueError:
        print("Invalid input. Please enter appropriate data types.\n")

def view_employee():
    if not employees:
        print("No employees available.\n")
        return

    print("\n{:<10} {:<15} {:<5} {:<15} {:<10}".format("ID", "Name", "Age", "Department", "Salary"))
    print("-" * 60)
    for emp_id, details in employees.items():
        print("{:<10} {:<15} {:<5} {:<15} {:<10}".format(
            emp_id, details['name'], details['age'], details['department'], details['salary']
        ))
    print()
def search_employee():
    try:
        emp_id=int(input("Enter employee id-"))
        if emp_id in employees:
            emp = employees[emp_id]
            print("\nEmployee Found:")
            print("Name      :" ,emp['name'])
            print("Age       :" ,emp['age'])
            print("Department:" ,emp['department'])
            print("Salary    :" ,emp['salary'],"\n")
        else:
            print("Employee not found.\n")
    except ValueError:
        print("Invalid ID format.\n")

def main_menu():
    while True:
        print("employee management system")
        print("1. Add Employee")
        print("2. View Employee")
        print("3. Search Employee")
        print("4. Exit")
        c=int(input("Enter your choice 1-4 -\n"))
        if c==1:
            add_employee()
        elif c==2:
            view_employee()
        elif c==3:
            search_employee()
        elif c==4:
            print ("Thank you for using Employee Management System :)")
            break
        else :print ("Invalid choice .Select between 1 to 4")
main_menu()
                              
