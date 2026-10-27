# Calculator

A simple Python calculator project with basic arithmetic operations and unit tests.

## Project overview

This project contains a small calculator implementation in [calc.py](./calc.py) and a unit test suite in [test_calc.py](./test_calc.py). It also includes a Jenkins pipeline configuration in [Jenkinsfile](./Jenkinsfile) to run the app, execute tests, and package a zip artifact.

## Included operations

The calculator supports:

- Addition
- Subtraction
- Multiplication
- Division

Division raises a `ValueError` when the divisor is zero.

## Files

- [calc.py](./calc.py) - Calculator logic
- [test_calc.py](./test_calc.py) - Unit tests for the calculator
- [Jenkinsfile](./Jenkinsfile) - CI pipeline for running the app and tests

## Running the application

From the project folder, run:

```bash
python3 calc.py

This prints a sample calculation using the add function.

Running tests

python3 -m unittest test_calc.py

Example usage

from calc import add, subtract, multiply, divide

print(add(2, 3))       # 5
print(subtract(10, 4)) # 6
print(multiply(2, 3))  # 6
print(divide(10, 2))   # 5.0

divide(10, 0)  # raises ValueError

CI pipeline
The Jenkins pipeline performs:

Runs the calculator application
Runs the unit tests
Packages the source files into a zip artifact
This project is intentionally lightweight and is useful as a basic example of Python arithmetic logic with automated testing.