# coding
#include <iostream>
using namespace std;
const int MAX_STUDENTS= 30; // Maximum number of students//
// Global arrays to store student data//
string roll_no[MAX_STUDENTS];
string name[MAX_STUDENTS];
string Class[MAX_STUDENTS];
string course[MAX_STUDENTS];
string mobile_no[MAX_STUDENTS];
string admission_year[MAX_STUDENTS];
int kl = 0; // Number of students entered
// function declaration//
void enter();
void show();
void search();
void update();
void Delete();
int main()
{
    int x;
    cout << "If you want to check details of a student for confirmation, press 1: ";
    cin >> x;
    if (x == 1)
    {
        cout << "Be ready for further questions.\n";
    }
    else
    {
        cout << "OK, thank you!\n";
        return 0; // Exit program if user doesn't want to continue.//
    }
    cout << "How many student details do you want to enter? ";
    cin >> kl;

    if (kl > 0 && kl <= MAX_STUDENTS)
    {
        enter(); // Call function to enter student details
    }
    else
    {
        cout << "Required data is not found, please update.\n";
    }
    int choice;
    while (true)
    {
cout << "\nEnter your choice:\n";
cout << "1. Enter new student details\n";
cout << "2. Show student details\n";
cout << "3. Search for a student\n";
cout << "4. Update student details\n";
cout << "5. Delete student data\n";
cout << "6. Exit\n";
cin >> choice;
        switch (choice)
        {
            case 1:
                enter();
                break;
            case 2:
                show();
                break;
            case 3:
                search();
                break;
            case 4:
                update();
                break;
            case 5:
                Delete();
                break;
            case 6:
                cout << "Exiting program.\n";
                return 0;
            default:
                cout << "Invalid input.\n";
                break;
        }
    }
    return 0;
}
void enter()
{
    for (int i = 0; i < kl; ++i)
    {
        cout << "\nEnter details for student " << i + 1 << ":\n";
        cout << "Roll No: ";
        cin >> roll_no[i];
        cout << "Name: ";
        cin >> name[i];
        cout << "Class: ";
        cin >> Class[i];
        cout << "Course: ";
        cin >> course[i];
        cout << "Mobile No: ";
        cin >> mobile_no[i];
        cout << "Admission Year: ";
        cin >> admission_year[i];
    }
}
void show()
{
    if (kl == 0)
    {
        cout << "No data entered yet.\n";
        return;
    }

    for (int i = 0; i < kl; ++i)
    {
        cout << "\nData of Student " << i + 1 << ":\n";
        cout << "Roll No: " << roll_no[i] << endl;
        cout << "Name: " << name[i] << endl;
        cout << "Class: " << Class[i] << endl;
        cout << "Course: " << course[i] << endl;
        cout << "Mobile No: " << mobile_no[i] << endl;
        cout << "Admission Year: " << admission_year[i] << endl;
    }
}
void search()
{
    if (kl == 0)
    {
        cout << "No data entered yet.\n";
        return;
    }
    string rollno;
    cout << "Enter the roll no of student: ";
    cin >> rollno;
    bool found = false;
    for (int i = 0; i < kl; ++i)
    {
        if (rollno == roll_no[i])
        {
            cout << "\nData of Student " << i + 1 << ":\n";
            cout << "Roll No: " << roll_no[i] << endl;
            cout << "Name: " << name[i] << endl;
            cout << "Class: " << Class[i] << endl;
            cout << "Course: " << course[i] << endl;
            cout << "Mobile No: " << mobile_no[i] << endl;
            cout << "Admission Year: " << admission_year[i] << endl;
            found = true;
            break; // Stop searching further
        }
    }

    if (!found)
    {
        cout << "Student with roll no " << rollno << " not found.\n";
    }
}
void update()
{
    if (kl == 0)
    {
        cout << "No data entered yet.\n";
        return;
    }
    string rollno;
    cout << "Enter the roll no of student you want to update: ";
    cin >> rollno;
    bool found = false;
    for (int i = 0; i < kl; ++i)
    {
        if (rollno == roll_no[i])
        {
            cout << "\nPrevious data:\n";
            cout << "Data of Student " << i + 1 << ":\n";
            cout << "Roll No: " << roll_no[i] << endl;
            cout << "Name: " << name[i] << endl;
            cout << "Class: " << Class[i] << endl;
            cout << "Course: " << course[i] << endl;
            cout << "Mobile No: " << mobile_no[i] << endl;
            cout << "Admission Year: " << admission_year[i] << endl;
            cout << "\nEnter new data:\n";
            cout << "Roll No: ";
            cin >> roll_no[i];
            cout << "Name: ";
            cin >> name[i];
            cout << "Class: ";
            cin >> Class[i];
            cout << "Course: ";
            cin >> course[i];
            cout << "Mobile No: ";
            cin >> mobile_no[i];
            cout << "Admission Year: ";
            cin >> admission_year[i];
            found = true;
            break; // Stop searching further
        }
    }

    if (!found)
    {
        cout << "Student with roll no " << rollno << " not found.\n";
    }
}
void Delete()
{
    if (kl == 0)
    {
        cout << "No data entered yet.\n";
        return;
    }
    int a;
    cout << "Are you sure you want to delete all data?\n";
    cout << "Press 1 to delete all records, otherwise press any other number: ";
    cin >> a;
    if (a == 1)
    {
        kl = 0; // Reset number of students to 0
        cout << "All records deleted.\n";
    }
    else
    {
        cout << "Data deletion cancelled.\n";
    }
}
