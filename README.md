#include <iostream>
#include <cmath>
#include <cstdlib>
#include <vector>
#include <algorithm>
#include <bitset>
using namespace std;
// Function declarations
void performBasicOperation();
void performTrigonometryOperation();
void performAlgebraicOperation();
void performLogarithmicOperation(); 
void performAdditionalOperation();
void performBinaryOperation();

int main() {
    int choice;

    do {
        // Display menu options
        cout << "Menu:\n";
        cout << "1. Basic Operation\n";
        cout << "2. Trigonometry Operation\n";
        cout << "3. Algebraic Operation\n";
        cout << "4. Logarithmic Operation\n";
        cout << "5. Additional Operation\n";
        cout << "6. Binary Operation\n";
        cout << "7. Exit\n";
        // Get user choice
        cout << "Enter your choice: ";
        cin >> choice;

        // Process user choice
        switch (choice) {
            case 1:
                cout << "You selected Basic Operation\n";
                performBasicOperation();
                break;
            case 2:
                cout << "You selected Trigonometry Operation\n";
                performTrigonometryOperation();
                break;
            case 3:
                cout << "You selected Algebraic Operation\n";
                performAlgebraicOperation();
                break;
            case 4:
                cout << "You selected Logarithmic Operations\n";
                performLogarithmicOperation(); 
                break;
            case 5:
                cout << "You selected Additional Operations\n";
                performAdditionalOperation();
                break;
            case 6:
                cout << "You selected Binary Operations\n";
                performBinaryOperation();
                break;
            case 7:
                cout << "Exiting the program. Goodbye!\n";
                break;
            default:
                cout << "Invalid choice. Please enter a valid option.\n";
        }

    } while (choice != 7);  // Continue the loop until the user selects option 9 to exit

    return 0;
}

// Function definition for basic operations
void performBasicOperation() {
    char operation;
    double num1, num2;

    cout << "Enter operation (+, -, *, /): ";
    cin >> operation;

    cout << "Enter two numbers: ";
    cin >> num1 >> num2;

    // Perform the calculation based on the chosen operation
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
            if (num2 != 0) {
                cout << "Result: " << num1 / num2 << endl;
            } else {
                cout << "Error: Division by zero is undefined." << endl;
            }
            break;
        default:
            cout << "Error: Invalid operation. Please enter +, -, *, or /." << endl;
            break;
    }
}
// Function definition for trigonometric operations
void performTrigonometryOperation() {
    char operation;
    double angle;

    cout << "Choose a trigonometric operation: \n";
    cout << "1. Sine\n2. Cosine\n3. Tangent\n4. Arcsine\n5. Arccosine\n6. Arctangent\n";
    cout << "Enter the operation number (1-6): ";
    cin >> operation;
    cout << "Enter the angle in degrees: ";
    cin >> angle;

    // Convert angle to radians for trigonometric functions
    double radianAngle = angle * M_PI / 180.0;

    switch (operation) {
        case '1':
            cout << "Sine(" << angle << ") = " << sin(radianAngle) << endl;
            break;
        case '2':
            cout << "Cosine(" << angle << ") = " << cos(radianAngle) << endl;
            break;
        case '3':
            cout << "Tangent(" << angle << ") = " << tan(radianAngle) << endl;
            break;
        case '4':
            cout << "Arcsine(" << angle << ") = " << asin(sin(radianAngle)) * 180.0 / M_PI << " degrees" << endl;
            break;
        case '5':
            cout << "Arccosine(" << angle << ") = " << acos(cos(radianAngle)) * 180.0 / M_PI << " degrees" << endl;
            break;
        case '6':
            cout << "Arctangent(" << angle << ") = " << atan(tan(radianAngle)) * 180.0 / M_PI << " degrees" << endl;
            break;
        default:
            cout << "Invalid operation number. Please enter a number between 1 and 6." << endl;
            break;
    }
}
// Function definition for algebraic operations
unsigned long long factorial(int n);
void performAlgebraicOperation() {
    char operation;
    double operand;

    cout << "Choose an operation:" << endl;
    cout << "1. Exponentiation\n2. Square Root\n3. Cube Root\n4. nth Root\n5. Factorial\n6. Absolute Value\n";
    cout << "Enter the operation number (1-6): ";
    cin >> operation;

    cout << "Enter the operand: ";
    cin >> operand;

    switch (operation) {
        case '1':
            cout << "Exponentiation: " << operand << " ^ 2 = " << pow(operand, 2) << endl;
            break;
        case '2':
            cout << "Square Root of " << operand << " = " << sqrt(operand) << endl;
            break;
        case '3':
            cout << "Cube Root of " << operand << " = " << cbrt(operand) << endl;
            break;
        case '4':
            int n;
            cout << "Enter the value of n for nth Root: ";
            cin >> n;
            cout << "nth Root of " << operand << " (where n = " << n << ") = " << pow(operand, 1.0/n) << endl;
            break;
        case '5':
            cout << "Factorial of " << operand << " = " << factorial(static_cast<int>(operand)) << endl;
            break;
        case '6':
            cout << "Absolute Value of " << operand << " = " << abs(operand) << endl;
            break;
        default:
            cout << "Invalid operation number. Please enter a number between 1 and 6." << endl;
            break;
    }
}

// Function definition for factorial
unsigned long long factorial(int n) {
    if (n < 0) {
        cerr << "Error: Factorial is not defined for negative numbers." << endl;
        exit(EXIT_FAILURE);
    }
    if (n == 0 || n == 1) {
        return 1;
    }
    return n * factorial(n - 1);
}
// Function definition for logarithmic operations
void performLogarithmicOperation() {
    char operation;
    double operand;

    cout << "Choose a logarithmic operation:" << endl;
    cout << "1. Logarithm (base 10)\n2. Natural Logarithm (base e)\n3. Custom Base Logarithm\n";
    cout << "Enter the operation number (1-3): ";
    cin >> operation;

    cout << "Enter the operand: ";
    cin >> operand;

    switch (operation) {
        case '1':
            cout << "Logarithm (base 10) of " << operand << " = " << log10(operand) << endl;
            break;
        case '2':
            cout << "Natural Logarithm (base e) of " << operand << " = " << log(operand) << endl;
            break;
        case '3':
            double base;
            cout << "Enter the base for custom base logarithm: ";
            cin >> base;
            if (base > 0 && base != 1) {
                cout << "Custom Base Logarithm (base " << base << ") of " << operand << " = " << log(operand) / log(base) << endl;
            } else {
                cerr << "Error: Logarithm is not defined for non-positive bases or base 1." << endl;
                exit(EXIT_FAILURE);
            }
            break;
        default:
            cout << "Invalid operation number. Please enter a number between 1 and 3." << endl;
            break;
    }
}
// Function to calculate Greatest Common Divisor (GCD)
unsigned long long gcd(unsigned long long a, unsigned long long b) {
    while (b != 0) {
        unsigned long long temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}

// Function to calculate Least Common Multiple (LCM)
unsigned long long lcm(unsigned long long a, unsigned long long b) {
    return (a * b) / gcd(a, b);
}

// Function to perform various operations
void performOperation(char operation, double num1, double num2) {
    switch (operation) {
        case '1':
            cout << "Modulus (remainder): " << static_cast<int>(num1) % static_cast<int>(num2) << endl;
            break;
        case '2':
            cout << "Percentage calculation: " << (num1 / num2) * 100 << "%" << endl;
            break;
        case '3':
            cout << "Greatest Common Divisor (GCD): " << gcd(static_cast<unsigned long long>(num1), static_cast<unsigned long long>(num2)) << endl;
            break;
        case '4':
            cout << "Least Common Multiple (LCM): " << lcm(static_cast<unsigned long long>(num1), static_cast<unsigned long long>(num2)) << endl;
            break;
        case '5':
            cout << "Floor (round down) of " << num1 << ": " << floor(num1) << endl;
            break;
        case '6':
            cout << "Ceiling (round up) of " << num1 << ": " << ceil(num1) << endl;
            break;
        default:
            cout << "Invalid operation number. Please enter a number between 1 and 6." << endl;
            break;
    }
}

// Function to perform additional operations
void performAdditionalOperation() {
    char operation;
    double num1, num2;

    cout << "Choose an operation:" << endl;
    cout << "1. Modulus (remainder)\n2. Percentage calculation\n";
    cout << "3. Greatest Common Divisor (GCD)\n4. Least Common Multiple (LCM)\n";
    cout << "5. Floor (round down)\n6. Ceiling (round up)\n";
    cout << "Enter the operation number (1-6): ";
    cin >> operation;

    cout << "Enter two numbers: ";
    cin >> num1 >> num2;

    performOperation(operation, num1, num2);
}
// Function to perform Binary operations

bitset<9> binaryAddition(const bitset<8>& binaryNum1, const bitset<8>& binaryNum2) {
    return bitset<9>(binaryNum1.to_ulong() + binaryNum2.to_ulong());
}

// Function to perform binary subtraction
bitset<9> binarySubtraction(const bitset<8>& binaryNum1, const bitset<8>& binaryNum2) {
    return bitset<9>(binaryNum1.to_ulong() - binaryNum2.to_ulong());
}

// Function to perform binary multiplication
bitset<16> binaryMultiplication(const bitset<8>& binaryNum1, const bitset<8>& binaryNum2) {
    return bitset<16>(binaryNum1.to_ulong() * binaryNum2.to_ulong());
}

// Function to perform binary division
bitset<16> binaryDivision(const bitset<8>& binaryNum1, const bitset<8>& binaryNum2) {
    if (binaryNum2.to_ulong() != 0) {
        return bitset<16>(binaryNum1.to_ulong() / binaryNum2.to_ulong());
    } else {
        cerr << "Error: Division by zero is undefined." << endl;
        exit(EXIT_FAILURE);
    }
}

// Function to perform binary AND operation
bitset<8> binaryAND(const bitset<8>& binaryNum1, const bitset<8>& binaryNum2) {
    return binaryNum1 & binaryNum2;
}

// Function to perform binary OR operation
bitset<8> binaryOR(const bitset<8>& binaryNum1, const bitset<8>& binaryNum2) {
    return binaryNum1 | binaryNum2;
}

// Function to perform binary XOR operation
bitset<8> binaryXOR(const bitset<8>& binaryNum1, const bitset<8>& binaryNum2) {
    return binaryNum1 ^ binaryNum2;
}

// Function to perform binary operations
void performBinaryOperation() {
    bitset<8> binaryNum1, binaryNum2;

    cout << "Enter binary number 1 (8 bits): ";
    cin >> binaryNum1;

    cout << "Enter binary number 2 (8 bits): ";
    cin >> binaryNum2;

    cout << "Binary Addition: " << binaryAddition(binaryNum1, binaryNum2) << endl;
    cout << "Binary Subtraction: " << binarySubtraction(binaryNum1, binaryNum2) << endl;
    cout << "Binary Multiplication: " << binaryMultiplication(binaryNum1, binaryNum2) << endl;
    cout << "Binary Division: " << binaryDivision(binaryNum1, binaryNum2) << endl;
    cout << "Binary AND: " << binaryAND(binaryNum1, binaryNum2) << endl;
    cout << "Binary OR: " << binaryOR(binaryNum1, binaryNum2) << endl;
    cout << "Binary XOR: " << binaryXOR(binaryNum1, binaryNum2) << endl;
}
