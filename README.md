#include <iostream>
#include <chrono>
using namespace std;
using namespace chrono;
long long iterativeFactorial(int n)
{
long long fact = 1;
for (int i = n; i >= 1; i--)
{
fact *= i;
}
return fact;
}
long long recursiveFactorial(int n)
{
if (n == 1 || n == 0)
return 1;
else
return n * recursiveFactorial(n - 1);
}
int main()
{
int n;
cout << "Enter the Number(n): ";
cin >> n;
if (n <= 0)
{
cout << "Please enter a positive integer" << endl;
}
else
{
// Measure the execution time of the iterative factorial function
auto start = high_resolution_clock::now();
long long iterativeResult = iterativeFactorial(n);
auto end = high_resolution_clock::now();
auto iterativeDuration = duration_cast<duration<double>>(end -
start).count();
// Print the result and execution time for the iterative factorial
cout << "The Factorial of " << n << " using iterative method is: " <<
iterativeResult << endl;
cout << "Time taken by iterative method: " << iterativeDuration << " 
seconds" << endl;
// Measure the execution time of the recursive factorial function
start = high_resolution_clock::now();
long long recursiveResult = recursiveFactorial(n);
end = high_resolution_clock::now();
auto recursiveDuration = duration_cast<duration<double>>(end -
start).count();
// Print the result and execution time for the recursive factorial
cout << "The Factorial of " << n << " using recursive method is: " <<
recursiveResult << endl;
cout << "Time taken by recursive method: " << recursiveDuration << " 
seconds" << endl;
}
 return 0;
}
