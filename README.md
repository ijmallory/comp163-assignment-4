# comp163-assignment-4
# This is a Semester Survival Simulator that executes "if/elif/else" and other operators such as "in, not in, and, or" to simulate a college students academic/social life. The "personal stats" can be modified to fit anyone.
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

# Study Strategy Decision
print("\nStudy Strategy Decision")
print("Which subject will you focus your study hours on?")
study_options = ["Programming", "Math", "English", "History"]
print(study_options)
study_focus = input("Your choice: ")
if study_focus in study_options:
    print(f"Focusing on **{study_focus}**.")
    if (study_hours >= 35) and (stress_level < 60):
        print("You're studying smart and keeping your stress low. Great combination!")
        current_gpa += 0.2
        social_points += 5

    elif (study_hours < 20) or (stress_level > 70):
        print("Your study habits are concerning. Stress or lack of effort will hurt your performance.")
        current_gpa -= 0.2
        social_points -= 5

    elif (study_focus not in ["Programming", "Math"]) and (current_gpa < 3.0):
        print("A key subject might be slipping. Focusing elsewhere might be a mistake right now.")
        current_gpa -= 0.1

    else:
        if not (current_gpa == 4.0):
            print("A solid effort. Keep up the good work.")
            current_gpa += 0.1
        else:
            print("You're already at a perfect GPA. Maintaining is the goal!")
    study_hours -= 10
else:
    print("That subject is not a valid option. Your study hours are wasted.")
    stress_level += 5

# Final Semester Assessment
print("\nFinal Semester Assessment")
print("Calculating final semester results...")

# Final GPA adjustment
if stress_level > 75:
    current_gpa -= 0.2
if social_points > 60:
    current_gpa += 0.1

# Ensure GPA is within bounds
if current_gpa > 4.0:
    current_gpa = 4.0
elif current_gpa < 1.0:
    current_gpa = 1.0

# Check the GPA to make sure it's a float
if type(current_gpa) is float:
    print("Assessment is valid (GPA is a float). Proceeding to final results.")
    if current_gpa >= 3.5:
        print("\n**End result A: Dean's List")
        if stress_level < 50:
            print("You excelled academically AND maintained a healthy balance!")
            if social_points > 50:
                print("Your success was well-rounded. Truly a successful semester.")
            else:
                print("You could have been a bit more social, but the grades are great.")
        else:
            print("You succeeded academically but burned out doing it. Next semester, find a better balance.")
    elif current_gpa >= 2.5:
        print("\n**End Result B: The Steady Grinder")
        if social_points >= 40:
            print("A solid performance. You passed all your classes while keeping your life in check.")
        else:
            print("It was a struggle, and you felt the pressure. Your effort was enough, but just barely.")
    else:
        print("\n**End Result C: The Semester Reset**")
        if social_points > 70:
            print("You prioritized fun over studying. Your social calendar was full, but your grades suffered.")
        else:
            print("It was a difficult semester overall. Bad planning led to poor results.")
else:
    if type(current_gpa) not in float:
        print("Error: The GPA variable is a incorrect type. Assessment failed")

# Display Final stats
print("\n" + "=" * 40)
print("FINAL SEMESTER STATISTICS")
print(f"  Final GPA: {current_gpa:.2f}")
print(f"  Remaining Study Hours: {study_hours}")
print(f"  Final Social Points: {social_points}")
print(f"  Final Stress Level: {stress_level}")
print("=" * 40)
