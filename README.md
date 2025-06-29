exams = {}

def add_exam():
    exam_id = input("Enter Exam ID: ")
    subject = input("Enter Subject: ")
    date = input("Enter Date (YYYY-MM-DD): ")
    time = input("Enter Time (e.g., 10:00 AM): ")
    exams[exam_id] = {"subject": subject, "date": date, "time": time}
    print("Exam added successfully.\n")

def view_exams():
    if not exams:
        print("No exams scheduled.\n")
        return
    for exam_id, details in exams.items():
        print(f"ID: {exam_id}, Subject: {details['subject']}, Date: {details['date']}, Time: {details['time']}")
    print()

def edit_exam():
    exam_id = input("Enter Exam ID to edit: ")
    if exam_id in exams:
        subject = input("Enter new Subject: ")
        date = input("Enter new Date (YYYY-MM-DD): ")
        time = input("Enter new Time (e.g., 10:00 AM): ")
        exams[exam_id] = {"subject": subject, "date": date, "time": time}
        print("Exam updated successfully.\n")
    else:
        print("Exam ID not found.\n")

def delete_exam():
    exam_id = input("Enter Exam ID to delete: ")
    if exam_id in exams:
        del exams[exam_id]
        print("Exam deleted successfully.\n")
    else:
        print("Exam ID not found.\n")

def menu():
    while True:
        print("=== Smart Scheduler ===")
        print("1. Add Exam")
        print("2. View Exams")
        print("3. Edit Exam")
        print("4. Delete Exam")
        print("5. Exit")
        choice = input("Choose an option (1-5): ")

        if choice == '1':
            add_exam()
        elif choice == '2':
            view_exams()
        elif choice == '3':
            edit_exam()
        elif choice == '4':
            delete_exam()
        elif choice == '5':
            print("Exiting program.")
            break
        else:
            print("Invalid choice. Try again.\n")
if __name__ == "__main__":
    menu()
