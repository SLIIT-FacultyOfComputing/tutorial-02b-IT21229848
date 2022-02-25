# IT1050-Tutorial-02

## Objectives : Convert C programs to C++
Use your Repl.IT account and use the Instructions provided by your Instructors to complete the Tutorial.  All instructions are in the GitHub classroom and Repl.it  for the Tutorial Questions for Week 02. Please submit your solutions by commiting code from Repl.it

/*Exercise 1 - Calculations

Convert the C program given below which converts a length given in cm to inches to a C++ program.

Please Note that the input command in C++ is std::cin. This is a representation of the Keyboard.

e.g.

float data1;
int data2;
scanf("%f", &data1); --> std::cin >> data1;
scanf("%d", &data2); --> std::cin >> data2; 
You already know that printf() in C is std::cout in C++ e.g.

printf("Hello World") --> std::cout << "Hello World";
2.54cm = 1 inch
*/

 

#include <iostream>
int main() 
{
    float cm, inches;
    using namespace std;

    cout<<"Enter a length in cm : ";
    cin>>cm;

    inches = cm / 2.54;
    cout<<"Length in inches is "<< inches << endl;

    return 0;
}  


/*Exercise 2 - Selection

Convert the C program given below which calculates an employee's salary to a C++ program.

Input Type, Salary, otHours

Type = 1
OtRate = 1000
Type = 2
OtRate = 1500
Type = 3
OtRate = 1700
Please Note that the input command in C++ is std::cin. This is a representation of the Keyboard.*/

#include <iostream>
int main()
{
   double salary, netSalary;
   int etype, otHrs, otRate;
   using namespace std;

   cout<<"Enter Employee Type : ";
   cin>>etype;

   cout<<"Enter Salary  : ";
   cin>>salary;

   cout<<"Enter OtHrs : ";
   cin>>otHrs; 
   
   switch (etype) {
      case 1 :
          otRate = 1000;
          break;
      case 2 :
          otRate = 1500;
          break;
      default :
          otRate = 1700;
          break;
   }


   netSalary = salary + otHrs * otRate;
   std::cout<<"Net Salary is " << netSalary;
  
   return 0;
}




/*Exercise 3 - Repeatition

Convert the C program given below which calculates the Factorial of a number that you input from the keyboard to a C++ program.

Please Note that the input command in C++ is std::cin. This is a representation of the Keyboard.*/

#include <iostream>
int main()
{
    using namespace std;
    int no;
    long fac;

    cout << "Enter a Number : ";
    cin >> no;

    fac = 1;
    for (int r=no; r >= 1; r--) {
        fac = fac * r;
    }

    // cout << "Factorial of %d is %ld\n", no, fac);  

    cout << "Factorial of " << no << " is " << fac << endl;  

    return 0;
}




/*Exercise 4 - Functions

Write a program to calculate the function called nCr which is defined as

nCr = n!/ r!(n−r)!
Where n! is the factorial of n.

Implement the functions

long Factorial(int no);
long nCr(int n, int r);
Do not modify the main function.*/

#include <iostream>

long Factorial(int no);
long nCr(int n, int r);

int main() {
  int n, r;
  std::cout << "Enter a value for n ";
  std::cin >> n;

  std::cout << "Enter a value for r ";
  std::cin >> r;

  std::cout << "nCr = ";
  std::cout << nCr(n,r);
  std::cout << std::endl;

  return 0;
}

long Factorial(int no)
{
  int i, num = 1;
  for (i = 1; i <= no; i++)
  {
    num = num * i;
  }
  return num;
}


long nCr(int n, int r)
{
  return Factorial(n)  / (Factorial(r) * Factorial(n - r));
}