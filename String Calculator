//
//  main.cpp
//  String Calculator
//
//  Created by Jennifer Luna on 9/18/24.
//

#include <iostream>
#include <string>
#include <sstream>
#include <vector>
#include <cassert>

using namespace std;

// Function to split the string based on delimiters (commas and semicolons)
vector<int> splitStringToNumbers(const string &input) {
    vector<int> numbers;
    string temp;
    stringstream ss(input);

    // Iterate through the string, separating by commas or semicolons
    while (getline(ss, temp, ',')) {
        stringstream tempSS(temp);
        string token;
        while (getline(tempSS, token, ';')) {
            if (!token.empty()) {
                numbers.push_back(stoi(token));
            }
        }
    }
    return numbers;
}

// Calculator function to sum the numbers in the string
int calculator(const string &input) {
    if (input.empty()) {
        return 0;
    }

    vector<int> numbers = splitStringToNumbers(input);
    int sum = 0;

    // Calculate the sum of the numbers
    for (int num : numbers) {
        sum += num;
    }

    return sum;
}

// Test cases using assert
void runTests() {
    assert(calculator("1,2,3") == 6);
    assert(calculator("4;7;8") == 19);
    assert(calculator("10") == 10);
    assert(calculator("0") == 0);
    assert(calculator("") == 0);
    assert(calculator("5,10;15,20") == 50);
    assert(calculator("100;200,300") == 600);

    cout << "All tests passed!" << endl;
}

int main() {
    runTests();
    return 0;
}
