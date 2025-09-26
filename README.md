# comp163-assignment-4
# Personal stats
student_name = 'Izeal Mallory'
current_gpa = 3.56  # Float between 1.0 and 4.0
study_hours = int(15)  # Integer (Ex. 25)
social_points = int(65)  # Integer (Ex. 50)
stress_level = int(30)  # Integer 0-100

# Display welcome message with personal stats
print("=" * 40)
print(f"Welcome, {student_name}, to the Semester Survival Simulator!")
print("Here are your starting stats:")
print(f"  GPA: {current_gpa:.2f}")
print(f"  Study Hours: {study_hours}")
print(f"  Social Points: {social_points}")
print(f"  Stress Level: {stress_level}")
print("=" * 40)

# Course Planning Decision
print("\nCourse Planning Decision")
print("Choose your course load:")
print("(A) Light (12 credits)")
print("(B) Standard (15 credits)")
print("(C) Heavy (18 credits)")

choice = input("Choose a choice: ")
if choice == 'A':
    print("You chose a LIGHT course load")
    if current_gpa >= 3.5:
        print("With your high GPA, this should be a breeze.")
        study_hours += 5
        stress_level -= 10
    else:
        print("A lighter load is a smart choice for balancing your semester.")
        study_hours += 10
        stress_level -= 10

elif choice == 'B':
    print("You chose a STANDARD course load")
    if current_gpa != 1.0:
        print("This is a balanced choice. Maintain focus!")
        study_hours += 15
        stress_level += 5
    else:
        print("This will require serious commitment. Be careful with your time.")
        study_hours += 20
        stress_level += 10

elif choice == 'C':
    print("You chose a HEAVY course load")
    if current_gpa >= 3.5:
        print("You're ambitious! Your current GPA suggests you can handle the challenge")
        study_hours += 25
        stress_level += 15
        social_points -= 5
    else:
        print("A heavy load is a risk with your current GPA. Prepare for long nights!")
        study_hours += 30
        stress_level += 25
        social_points -= 10

else:
    print("Invalid choice. You will receive a standard load by default.")
    study_hours += 15
    stress_level += 5
