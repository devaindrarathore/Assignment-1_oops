#include <iostream>

using namespace std;

int main()
{
    string Subjects[] = {"DCF", "UXD", "DBMS", "OOP", "WA"};
    int Marks[5];
    int Total = 0;
    int FailedSubjects = 0;
    double Percentage;

    for (int i = 1; i <= 5; i++) {
        cout << "Enter marks for " << Subjects[i] << " = ";
        cin >> Marks[i];

        if (Marks[i] < 0 || Marks[i] > 100) {
            cout << "Invalid marks. Please enter a value between 0 and 100." << endl;
            i--;
        }
        else
            {
            Total = Total + Marks[i];
            if (Marks[i] < 50) {
                FailedSubjects++;
            }
        }
    }

    // Calculating the Percentage
    Percentage = (double)Total / 500*100;

    // Result Declaration
    if (FailedSubjects == 0)
    {
        cout << "Result : Pass" << endl;
        if (Percentage >= 70) {
            cout << "Division: First" << endl;
        } else if (Percentage >= 60) {
            cout << "Division: Second" << endl;
        } else {
            cout << "Division: Third" << endl;
        }
        cout << "Percentage : " << Percentage << "%" << endl;
    }
    else if (FailedSubjects == 1)
    {
        // Check for grace marks

        if (Marks[1] == 47 || Marks[2] == 47 || Marks[3] == 47 || Marks[4] == 47 || Marks[5] == 47)
        {
            cout << "Result : Pass with grace of 3 in ";
            if (Marks[1] == 47 && Marks[1] <= 49) {
                cout << Subjects[1];
            } else if (Marks[2] >= 47 && Marks[2] <= 49) {
                cout << Subjects[2];
            } else if (Marks[3] >= 47 && Marks[3] <= 49) {
                cout << Subjects[3];
            } else if (Marks[4] >= 47 && Marks[4] <= 49) {
                cout << Subjects[4];
            }
        }
        else if (Marks[1] == 48 || Marks[2] == 48 || Marks[3] == 48 || Marks[4] == 48 || Marks[5] == 48)
        {
            cout << "Result : Pass with grace of 2 in ";

            if (Marks[1] >= 48 && Marks[1] <= 49) {
                cout << Subjects[1];
            } else if (Marks[2] >= 48 && Marks[2] <= 49) {
                cout << Subjects[2];
            } else if (Marks[3] >= 48 && Marks[3] <= 49) {
                cout << Subjects[3];
            } else if (Marks[4] >= 48 && Marks[4] <= 49) {
                cout << Subjects[4];
            } else if (Marks[5] >= 48 && Marks[5] <= 49) {
                cout << Subjects[5];
            }
        }
        else if (Marks[1] == 49 || Marks[2] == 49 || Marks[3] == 49 || Marks[4] == 49 || Marks[5] == 49)
        {
            cout << "Result : Pass with grace of 1 in ";

            if (Marks[1] >= 49 && Marks[1] <= 49) {
                cout << Subjects[1] ;
            } else if (Marks[2] >= 49 && Marks[2] <= 49) {
                cout << Subjects[2];
            } else if (Marks[3] >= 49 && Marks[3] <= 49) {
                cout << Subjects[3];
            } else if (Marks[4] >= 49 && Marks[4] <= 49) {
                cout << Subjects[4];
            } else if (Marks[5] >= 49 && Marks[5] <= 49) {
                cout << Subjects[5];
            }
        }
        else
        {
            cout << "Result : Supplementary " << endl;
        }
    }
     else
    {
        cout << "Result : Fail " << endl;
    }

    return 0;
}
