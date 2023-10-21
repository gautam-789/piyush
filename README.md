DAY 34
#include <stdio.h>

// Function to determine if Chef can set the desired temperature for a perfect bath
void can_set_temperature(int T, int test_cases[][4]) {
    for (int i = 0; i < T; i++) {
        int A = test_cases[i][0];
        int B = test_cases[i][1];
        int X = test_cases[i][2];
        int Y = test_cases[i][3];
        
        // Calculate the final temperature after mixing hot and cold water
        int final_temp = A + X - Y;
        
        // Check if the final temperature matches the desired temperature or is within 1 degree
        if (final_temp == B || final_temp + 1 == B || final_temp - 1 == B) {
            printf("YES\n");
        } else {
            printf("NO\n");
        }
    }
}

int main() {
    int T;
    scanf("%d", &T); // Read the number of test cases
    
    int test_cases[T][4]; // Initialize a 2D array to store test cases
    
    // Read input test cases
    for (int i = 0; i < T; i++) {
        scanf("%d %d %d %d", &test_cases[i][0], &test_cases[i][1], &test_cases[i][2], &test_cases[i][3]);
    }
    
    // Call the function to check and print the results
    can_set_temperature(T, test_cases);
    
    return 0;
}