#include <iostream>
#include <cmath>     
#include <limits>    

using namespace std;

void clearInput() {
    cin.clear(); 
    cin.ignore(numeric_limits<streamsize>::max(), '\n'); 
}

int main() {
    char operation;
    double num1, num2;
    bool keepRunning = true;

    cout << "=== Calculator ===" << endl;
    cout << "Supported operations: + - * / ^ % (output: q)" << endl;

    while (keepRunning) {
        cout << "\nEnter an operation: ";
        cin >> operation;

        if (operation == 'q') {
            keepRunning = false;
            break;
        }

        cout << "Enter a number: ";
        while (!(cin >> num1)) {
            cout << "Invalid input. Please enter a number: ";
            clearInput();
        }

        cout << "Enter a number: ";
        while (!(cin >> num2)) {
            cout << "Invalid input. Please enter a number: ";
            clearInput();
        }

        switch (operation) {
        case '+':
            cout << "Result: " << num1 + num2 << endl;
            break;
        case '-':
            cout << "Result: " << num1 - num2 << endl;
            break;
        case '*':
            cout << "Result: " << num1 * num2 << endl;
            break;
        case '/':
            if (num2 == 0) {
                cout << "Error: Division by 0!" << endl;
            }
            else {
                cout << "Result: " << num1 / num2 << endl;
            }
            break;
        case '^':
            cout << "Result: " << pow(num1, num2) << endl;
            break;
        case '%':
            if ((int)num2 == 0) {
                cout << "Error: Division by 0!" << endl;
            }
            else {
                cout << "Result: " << fmod(num1, num2) << endl;
            }
            break;
        default:
            cout << "Unknown operation." << endl;
            break;
        }
    }

    cout << "\n End of the program." << endl;
    return 0;
}
