Shamir's Secret Sharing Solver
This project implements a simplified version of Shamir's Secret Sharing algorithm, designed to solve a polynomial based on a set of encoded points and determine the secret (constant term c) of the polynomial.

Features
Polynomial Solving: Determines the constant term of a polynomial using the given points.
Base Conversion: Decodes points encoded in various number bases.
Gaussian Elimination: Uses Gaussian Elimination to solve the system of equations generated from the given points.
Error Detection: Identifies points that don't lie on the reconstructed polynomial curve (wrong points).
Files
main.c: Contains the source code that solves the problem.
README.md: This documentation file.
Prerequisites
To compile and run this C program, you need:

C Compiler (GCC or any other standard C compiler)
Terminal/Command Prompt for compilation and execution
Installation and Compilation
Download/Clone the repository: You can clone this repository using Git or download the source code directly.

bash
Copy code
git clone https://github.com/your-username/shamir-secret-sharing.git
cd shamir-secret-sharing
Compile the C program: You need to compile the main.c file using a C compiler. For example, using GCC:

bash
Copy code
gcc main.c -o secret_solver -lm
The -lm flag links the math library since we are using mathematical functions such as pow and fabs.

Run the executable:

After compilation, you can run the program as follows:

bash
Copy code
./secret_solver
Usage
The program comes with two pre-defined test cases (Test Case 1 and Test Case 2).

Test Case 1
json
Copy code
{
  "keys": {
    "n": 4,
    "k": 3
  },
  "points": [
    { "base": 10, "value": "4" },
    { "base": 2, "value": "111" },
    { "base": 10, "value": "12" },
    { "base": 4, "value": "213" }
  ]
}
Test Case 2
json
Copy code
{
  "keys": {
    "n": 9,
    "k": 6
  },
  "points": [
    { "base": 10, "value": "28735619723837" },
    { "base": 16, "value": "1A228867F0CA" },
    { "base": 12, "value": "32811A4AA0B7B" },
    { "base": 11, "value": "917978721331A" },
    { "base": 16, "value": "1A22886782E1" },
    { "base": 10, "value": "28735619654702" },
    { "base": 14, "value": "71AB5070CC4B" },
    { "base": 9, "value": "122662581541670" },
    { "base": 8, "value": "642121030037605" }
  ]
}
Output:
Secret: The constant term (c) of the polynomial.
Wrong Points: If there are any points that don't lie on the curve, they are listed.
Example Output:
yaml
Copy code
Test Case 1:
Secret: 1

Test Case 2:
Secret: 123456789
Wrong points: 3 7
Explanation:
Test Case 1: Calculates the constant term of the polynomial as 1.
Test Case 2: Identifies two points that don't fit on the polynomial curve (3 and 7).
Code Explanation
decode_value(): Converts the encoded Y-values from various bases into decimal form.

gaussian_elimination(): Solves the system of linear equations using Gaussian Elimination to find the polynomial coefficients.

find_secret(): Constructs the system of equations from the given points, solves for the polynomial, and returns the constant term.

is_point_on_curve(): Checks if a given point lies on the polynomial curve.

# Catalog
