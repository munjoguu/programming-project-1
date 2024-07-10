# hello-world 1st Lysa's project
//program to compute co curricular activities for new students
#include <iostream>
#include <vector>
#include <string>

using namespace std;

struct Student {
    string firstname;
    string surname;
    string gender;
    int age;
    string bbitGroup;
    string sport;
    vector<string> clubs;
};

vector<Student> students;
vector<string> sports = { "Rugby", "Athletics", "Swimming", "Soccer" };
vector<string> clubs = { "Journalism Club", "Red Cross Society", "AISEC", "Business Club", "Computer Science Club" };

void addStudent() {
    Student student;

    cout << "Enter student's first name: ";
    cin >> student.firstname;

    cout << "Enter student's surname: ";
    cin >> student.surname;

    cout << "Enter student's gender: ";
    cin >> student.gender;

    cout << "Enter student's age: ";
    cin >> student.age;

    cout << "Enter student's BBIT group: ";
    cin >> student.bbitGroup;

    // Select sport
    if (student.gender == "Male" || student.gender == "Female") {
        cout << "Select a sport from the following options:\n";
        for (int i = 0; i < sports.size(); i++) {
            cout << i + 1 << ". " << sports[i] << endl;
        }
        int choice;
        cin >> choice;
        student.sport = sports[choice - 1];
    }

    // Select clubs
    if (student.sport.empty() || student.clubs.size() < 3) {
        cout << "Select up to 3 clubs from the following options (enter 0 to finish):\n";
        for (int i = 0; i < clubs.size(); i++) {
            cout << i + 1 << ". " << clubs[i] << endl;
        }
        int choice;
        cin >> choice;
        while (choice != 0 && student.clubs.size() < 3) {
            student.clubs.push_back(clubs[choice - 1]);
            cin >> choice;
        }
    }

    students.push_back(student);
    cout << "Student added successfully!\n";
}

void viewStudents() {
    cout << "Viewing all students:\n";
    for (int i = 0; i < students.size(); i++) {
        cout << "Student " << i + 1 << ":\n";
        cout << "First Name: " << students[i].firstname << endl;
        cout << "Surname: " << students[i].surname << endl;
        cout << "Gender: " << students[i].gender << endl;
        cout << "Age: " << students[i].age << endl;
        cout << "BBIT Group: " << students[i].bbitGroup << endl;
        if (!students[i].sport.empty()) {
            cout << "Sport: " << students[i].sport << endl;
        }
        if (!students[i].clubs.empty()) {
            cout << "Clubs: ";
            for (int j = 0; j < students[i].clubs.size(); j++) {
                cout << students[i].clubs[j] << ", ";
            }
            cout << endl;
        }
        cout << endl;
    }
}

void viewClubs() {
    cout << "Viewing all clubs and societies:\n";
    for (int i = 0; i < clubs.size(); i++) {
        cout << i + 1 << ". " << clubs[i] << endl;
    }
}

void viewSports() {
    cout << "Viewing all sports:\n";
    for (int i = 0; i < sports.size(); i++) {
        cout << i + 1 << ". " << sports[i] << endl;
    }
}

void viewGroupedStudents() {
    cout << "Viewing students by group:\n";
    cout << "Enter BBIT group: ";
    string group;
    cin >> group;

    cout << "Students in group " << group << ":\n";
    for (int i = 0; i < students.size(); i++) {
        if (students[i].bbitGroup == group) {
            cout << "Student " << i + 1 << ":\n";
            cout << "First Name: " << students[i].firstname << endl;
            cout << "Surname: " << students[i].surname << endl;
            cout << "Gender: " << students[i].gender << endl;
            cout << "Age: " << students[i].age << endl;
            cout << "BBIT Group: " << students[i].bbitGroup << endl;
            if (!students[i].sport.empty()) {
                cout << "Sport: " << students[i].sport << endl;
            }
            if (!students[i].clubs.empty()) {
                cout << "Clubs: ";
                for (int j = 0; j < students[i].clubs.size(); j++) {
                    cout << students[i].clubs[j] << ", ";
                }
                cout << endl;
            }
            cout << endl;
        }
    }
}

void saveFiles() {
    // Save data to a csv or excel file
    cout << "Data saved successfully!\n";
}

int main() {
    int choice;

    do {
        cout << "Co-curricular Activity Selection System\n";
        cout << "1. Add Student\n";
        cout << "2. View Students\n";
        cout << "3. View Clubs/Societies\n";
        cout << "4. View Sports\n";
        cout << "5. View Grouped Students\n";
        cout << "6. Save all Files\n";
        cout << "7. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
        case 1:
            addStudent();
            break;
        case 2:
            viewStudents();
            break;
        case 3:
            viewClubs();
            break;
        case 4:
            viewSports();
            break;
        case 5:
            viewGroupedStudents();
            break;
        case 6:
            saveFiles();
            break;
        case 7:
            cout << "Exiting program...\n";
            break;
        default:
            cout << "Invalid choice. Please try again.\n";
            break;
        }

    } while (choice != 7);

    return
  
  
  
  
  
About
this repository is for a program

Resources
 Readme
 Activity
Stars
 0 stars
Watchers
 1 watching
Forks
 0 forks
Report repository
Releases
No releases published
Create a new release
Packages
No packages published
Publish your first package
Footer
© 2024 GitHub, Inc.

