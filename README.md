# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
## 11. Implementation of the concept of pointer to function.
## 12. Implementation of programs using structure and union.
## 13. Implementation of programs for different storage classes.
# Ex.No:26
  Develop a C program using static storage class in function with parameter and without return to display the incremental float values as indicated in the following output.
| Input | Output                                       |
|-------|----------------------------------------------|
| 1     | 101.25&nbsp;&nbsp;201.50&nbsp;&nbsp;301.75&nbsp;&nbsp;402.00&nbsp;&nbsp;502.75 |
# Date : 18/12/2025
# Aim:
To develop a C program using the static storage class in a function with a parameter and without a return value to display the required output.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  a. Declare an integer variable `input` to store the user’s number.  
  b. Inside the function `display(int n)`, declare a static float variable `base` and initialize it to 100.25.
### Step 4:
  Read an integer from the user and store it in `input`.
### Step 5:
  Call the function `display(input)` five times.
### Step 6:
  Inside the `display` function, for each call:  
  a. Calculate the sum of `base` and `n`.  
  b. Display the value.  
  c. Increase the value of `base` by 100.25.
### Step 7:
  Repeat Step 6 for all function calls.
### Step 8:
  Stop
# Program:
```
#include <stdio.h>

// Step 3b: Function definition
void display(int n)
{
    // Static variable retains its value across function calls
    static float base = 100.25;
    float sum;

    // Step 6a: Calculate sum
    sum = base + n;

    // Step 6b: Display the sum
    printf("Sum of base and input: %.2f\n", sum);

    // Step 6c: Increment base
    base += 100.25;
}

int main()
{
    int input;

    // Step 4: Read integer from user
    printf("Enter an integer: ");
    scanf("%d", &input);

    // Step 5: Call display function five times
    for (int i = 0; i < 5; i++)
    {
        display(input);
    }

    return 0;
}

```
# Output:
<img width="429" height="365" alt="image" src="https://github.com/user-attachments/assets/d15fb597-3c5e-439f-8d96-681bbbe5c3dd" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
# Ex.No:27
  Implement a C program to perform arithmetic operations (addition, subtraction, multiplication, division) on two integers using function pointers. The user should input two numbers and select the desired operation from a menu.
# Date :18/12/2025 
# Aim:
  To implement a C program that uses function pointers to perform arithmetic operations (add, subtract, multiply, divide) on two integers based on user choice.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  Declare four functions to perform arithmetic operations:  
  - `add(int a, int b)`  
  - `subtract(int a, int b)`  
  - `multiply(int a, int b)`  
  - `divide(int a, int b)`
### Step 4:
  Declare a function pointer `int (*operation)(int, int)` to point to any of the arithmetic functions.
### Step 5:
  Input two integers from the user (`num1` and `num2`).
### Step 6:
  Display a menu for the user to choose an operation:  
  - Add  
  - Subtract  
  - Multiply  
  - Divide
### Step 7:
  Read the user’s choice.
### Step 8:
  Use a switch statement to assign the function pointer `operation` to the appropriate function based on the user’s choice.  
  - **Step 8.1:** If the choice is 4 (divide), check if the second number is zero. If yes, display an error and terminate.  
  - **Step 8.2:** If the choice is invalid, display an error and terminate.
### Step 9:
  Call the function using the function pointer and store the result in a variable `result`.
### Step 10:
  Display the result.
### Step 11:
  Stop
# Program:
```
#include <stdio.h>

// Step 3: Arithmetic function definitions
int add(int a, int b)
{
    return a + b;
}

int subtract(int a, int b)
{
    return a - b;
}

int multiply(int a, int b)
{
    return a * b;
}

int divide(int a, int b)
{
    return a / b;
}

int main()
{
    int num1, num2, choice, result;
    // Step 4: Function pointer declaration
    int (*operation)(int, int) = NULL;

    // Step 5: Input two integers
    printf("Enter two integers: ");
    scanf("%d %d", &num1, &num2);

    // Step 6: Display menu
    printf("Choose an operation:\n");
    printf("1. Add\n2. Subtract\n3. Multiply\n4. Divide\n");
    printf("Enter your choice: ");
    scanf("%d", &choice);

    // Step 8: Assign function pointer based on choice
    switch (choice)
    {
    case 1:
        operation = add;
        break;
    case 2:
        operation = subtract;
        break;
    case 3:
        operation = multiply;
        break;
    case 4:
        if (num2 == 0)
        {
            printf("Error: Division by zero!\n");
            return 1;
        }
        operation = divide;
        break;
    default:
        printf("Invalid choice!\n");
        return 1;
    }

    // Step 9: Call function using pointer
    result = operation(num1, num2);

    // Step 10: Display result
    printf("Result: %d\n", result);

    return 0;
}

```
# Output:
<img width="409" height="419" alt="image" src="https://github.com/user-attachments/assets/9e46d75f-9e75-41e7-a37e-0af86e4483d6" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
# Ex.No:28
  Develop a C program to store details of n employees (employee number, name, and salary) using structures, and display the employee(s) with the highest salary.
# Date : 18/12/2025
# Aim:
  To develop and implement a C program that uses a structure to store employee details (employee number, name, and salary) and determine the employee(s) with the highest salary.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  Define a structure `employee` with the following members:  
  - `eno` (employee number)  
  - `ename` (employee name)  
  - `salary` (employee salary)
### Step 4:
  Declare an array of structures to store details of multiple employees.
### Step 5:
  Input the number of employees, `n`.
### Step 6:
  For each employee (`i = 0` to `n-1`), do the following:  
  - **Step 6.1:** Input employee number.  
  - **Step 6.2:** Input employee name (allow spaces).  
  - **Step 6.3:** Input employee salary.  
  - **Step 6.4 (Optional):** Print the entered details for verification.
### Step 7:
  Initialize a variable `high` with the salary of the first employee.
### Step 8:
  For each employee (`i = 1` to `n-1`), do the following:  
  - **Step 8.1:** Compare employee salary with `high`.  
  - **Step 8.2:** If the salary is greater than `high`, update `high` with this salary.
### Step 9:
  Print the details of employee(s) whose salary matches `high`:  
  - **Step 9.1:** Loop through all employees.  
  - **Step 9.2:** If employee salary equals `high`, print employee number, name, and salary.
### Step 10:
  Stop
# Program:
```
#include <stdio.h>

// Step 3: Define structure for employee
struct employee {
    int eno;
    char ename[50];
    float salary;
};

int main() {
    int n, i;
    float high;

    // Step 4 & 5: Input number of employees
    printf("Enter number of employees: ");
    scanf("%d", &n);

    struct employee emp[n];

    // Step 6: Input employee details
    for(i = 0; i < n; i++) {
        printf("\nEnter details for employee %d:\n", i + 1);

        printf("Employee Number: ");
        scanf("%d", &emp[i].eno);

        printf("Employee Name: ");
        getchar(); // To consume leftover newline
        fgets(emp[i].ename, sizeof(emp[i].ename), stdin);

        // Remove newline character from fgets
        size_t len = 0;
        while(emp[i].ename[len] != '\0') len++;
        if(emp[i].ename[len-1] == '\n') emp[i].ename[len-1] = '\0';

        printf("Employee Salary: ");
        scanf("%f", &emp[i].salary);
    }

    // Step 7: Initialize highest salary
    high = emp[0].salary;

    // Step 8: Find highest salary
    for(i = 1; i < n; i++) {
        if(emp[i].salary > high) {
            high = emp[i].salary;
        }
    }

    // Step 9: Display employee(s) with highest salary
    printf("\nEmployee(s) with highest salary %.2f:\n", high);
    for(i = 0; i < n; i++) {
        if(emp[i].salary == high) {
            printf("Employee Number: %d\n", emp[i].eno);
            printf("Employee Name: %s\n", emp[i].ename);
            printf("Employee Salary: %.2f\n\n", emp[i].salary);
        }
    }

    return 0;
}
```
# Output:
<img width="510" height="648" alt="image" src="https://github.com/user-attachments/assets/3fb974a3-f26a-41ea-b4fc-7c289d8c3011" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
# Ex.No:29
  Create the C program to calculate the present age of a person by passing structure as a reference.
# Date : 18/12/2025
# Aim:
  To create a C program that uses a structure to store the current date and birth date, and to calculate the person’s present age in years, months, and days by passing the structure as a reference.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  Define a structure named `date` with members to store:  
  - Current date (`c_date`, `c_month`, `c_year`)  
  - Birth date (`b_date`, `b_month`, `b_year`)  
  - Calculated age (`cal_date`, `cal_month`, `cal_year`)
### Step 4:
  Initialize a structure variable with the current date and birth date values.
### Step 5:
  Pass the structure variable to a function `findAge()` by reference.
### Step 6:
  Inside `findAge()`:  
  - a. Declare an integer array `month[]` to store the number of days in each month.  
  - b. If the birth date is greater than the current date:  
     - Add the number of days of the previous month to the current date.  
     - Decrease the current month by 1.  
  - c. If the birth month is greater than the current month:  
     - Decrease the current year by 1.  
     - Add 12 to the current month.  
  - d. Calculate the age in days, months, and years by subtracting the corresponding birth values from the current values.
### Step 7:
  Return the structure pointer containing the calculated age.
### Step 8:
  Display the calculated age (years, months, and days) in the `main` function.
### Step 9:
  Stop
# Program:
```
#include <stdio.h>
struct date {
    int c_date, c_month, c_year;
    int b_date, b_month, b_year; 
    int cal_date, cal_month, cal_year;
};
void findAge(struct date *d) {
    int month[] = {31,28,31,30,31,30,31,31,30,31,30,31};
    if(d->b_date > d->c_date) {
        d->c_date += month[(d->c_month - 2 + 12) % 12]; 
        d->c_month -= 1;
    }
    if(d->b_month > d->c_month) {
        d->c_year -= 1;
        d->c_month += 12;
    }
    d->cal_date = d->c_date - d->b_date;
    d->cal_month = d->c_month - d->b_month;
    d->cal_year = d->c_year - d->b_year;
}

int main() {
    struct date d;
    printf("Enter current date (DD MM YYYY): ");
    scanf("%d %d %d", &d.c_date, &d.c_month, &d.c_year);

    printf("Enter birth date (DD MM YYYY): ");
    scanf("%d %d %d", &d.b_date, &d.b_month, &d.b_year);
    findAge(&d);
    printf("\nPresent Age: %d years, %d months, %d days\n",
           d.cal_year, d.cal_month, d.cal_date);

    return 0;
}

```
# Output:
<img width="557" height="420" alt="image" src="https://github.com/user-attachments/assets/1f89410b-a197-4e49-8b87-d9de6af91b29" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M6
# IAPR-6- Module 6 - FoC
# Ex.No:30
  Build a C program to demonstrate the use of a pointer to a union. Store an integer value in a union, access it using a union pointer, and display it as both an integer and a character.
# Date :18/12/2025 
# Aim:
  To build a program in C that uses a pointer to a union to store an integer value and display it in both integer and character format.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3:
  Define a union `abc` with the following members:  
  - `int a`  
  - `char b`
### Step 4:
  Declare a union variable `var` of type `abc`.
### Step 5:
  Declare a pointer `ptr` of type `union abc*`.
### Step 6:
  Assign the address of `var` to `ptr`.
### Step 7:
  Store an integer value (e.g., 90) in `var.a`.
### Step 8:
  Access and print the value of `a` using the pointer `ptr` in integer format.
### Step 9:
  Access and print the same value using the pointer `ptr` in character format.
### Step 10:
  Stop
# Program:
```
#include <stdio.h>

// Step 3: Define a union
union abc {
    int a;
    char b;
};

int main() {
    // Step 4: Declare union variable
    union abc var;

    // Step 5: Declare pointer to union
    union abc *ptr;

    // Step 6: Assign address of var to ptr
    ptr = &var;

    // Step 7: Store an integer value
    var.a = 90;

    // Step 8: Print integer value using pointer
    printf("Integer value: %d\n", ptr->a);

    // Step 9: Print character value using pointer
    printf("Character value: %c\n", ptr->b);

    return 0;
}

```
# Output:
<img width="499" height="292" alt="image" src="https://github.com/user-attachments/assets/8feff9ad-2dd8-4e84-9e32-329a8fe494ff" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


