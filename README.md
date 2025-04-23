#student management system using python
    
    students = []

    def add_student(roll, name, course, cgpa):
    student = {
        'roll': roll,
        'name': name,
        'course': course,
        'cgpa': cgpa
    }
    students.append(student)
    print("Student added successfully!")

    def display_students():
    if not students:
        print("No students available.\n")
        return
    for s in students:
        print(f"Roll Number: {s['roll']}")
        print(f"Name: {s['name']}")
        print(f"Course: {s['course']}")
        print(f"CGPA: {s['cgpa']}")
        print("------------------------")

    def search_student(roll):
    for s in students:
        if s['roll'] == roll:
            print("Student Found:")
            print(f"Name: {s['name']}")
            print(f"Course: {s['course']}")
            print(f"CGPA: {s['cgpa']}\n")
            return
        print("Student not found.\n")

    def cgpa(roll, new_cgpa):
    for s in students:
        if s['roll'] == roll:
            s['cgpa'] = new_cgpa
            print("CGPA updated successfully!\n")
            return
    print("Student not found.\n")

    def delete_student(roll):
    for s in students:
        if s['roll'] == roll:
            students.remove(s)
            print("Student deleted successfully!\n")
            return
    print("Student not found.\n")

    def menu():
    while True:
        print("\n*** Student Management System ***")
        print("1. Add Student")
        print("2. Display All Students")
        print("3. Search Student")
        print("4. CGPA")
        print("5. Delete Student")
        print("6. Exit")

        choice = input("Enter your choice: ")

        if choice == '1':
            roll = int(input("Enter Roll Number: "))
            name = input("Enter Name: ")
            course = input("Enter Course: ")
            cgpa = float(input("Enter CGPA: "))
            add_student(roll, name, course, cgpa)

        elif choice == '2':
            display_students()

        elif choice == '3':
            roll = int(input("Enter Roll Number to Search: "))
            search_student(roll)

        elif choice == '4':
            roll = int(input("Enter Roll Number to Update CGPA: "))
            new_cgpa = float(input("Enter New CGPA: "))
            cgpa(roll, new_cgpa)

        elif choice == '5':
            roll = int(input("Enter Roll Number to Delete: "))
            delete_student(roll)

        elif choice == '6':
            print("Exiting program.")
            break

        else:
            print("Invalid choice! Try again.")

    menu()
