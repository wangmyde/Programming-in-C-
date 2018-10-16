# Basic syntax in C++
## 2.1 Expressions and Statements
Expressions are code sequences of operators and operands, computing a value from the operands, while a statement represents a concluded expression.

    c = a + b;
The part on the right side of the equals sign, (a + b). is an expression. The entire line is a statement.

## 2.2 Variables declaration
Variables are reserved memory locations to store values.
> The name of a variable can begin with an underscore.(**NOT GOOD**) 
> A variable must **not** begin with a number
> You must declare the type of a variable before you can define the variable.

## 2.3 Initializing variables
The initialization assigns a value to the variable.
Random numbers are assigned to variables that are declared but not initialized.

## 2.4 Cast operator
Syntax: (data type)(variable)

    #include <cstdlib>
    #include <iostream>
    using namespace std;
    int main()
    {
      int a=5, b=2;
      float c;
      c=(float)(a)/(float)(b);
      cout << "c = " << c << endl;
      system("pause");
     }
Result: 2.5

## 2.5 Constants
If you put the keyword const in front of the data type, a variable can only be read, i. e. the value of the variable can only be set during its initialization and therefore cannot be altered later in the further course of the source code.

    const double pi = 3.14159;

## 2.6 Functions
`return_type function_name(argumen_type_1 arg_1, argument_type_2 arg_2, ..., argument_type_n arg_n);`
The declaration specifies the data type of the return value (ret_type) and the name of the function (function_name). It also determines the order (arg_1, arg_2,..., arg_n) and the data types (argtype_1, ar-gtype_2,..., argtype_n) of the data arguments that will be passed to the function.

At least the data type of the return value and the data types of the input parameters must be specified in the prototype.

    int function(int,float,float); // 1 return value, 3 input parameters
    void function(); // no input parameters, no return value

## 2.7 Definition of a function statement
    ret_type function_name(argtype_1 arg_1, argtype_2 arg_2,..., argtype_n arg_n)
    {
      Statement;
      return ret_type; // Type of the variable or value must be the same as ret_type
    }
1. If the function prototype contains a return value, the definition must also contain a return statement that returns the value.
2. If the value void is returned, the return statement can be omitted or `return 0;` can be used.
3. If no return statement has been specified, the function will automatically return when the end of the function block is reached (the closing curly bracket).

## 2.8 Calling a function
To call a function, you need to pass the function name along with a list of the required parameters (within brackets, separated by commas). A function can take no or any number of parameters, but it can only return one or no value.
    
    using namespace std;
    int multiply(int, int); // Prototypes of the multiply and showResult functions
    void showResult(int);
	int main()
	{
		int result; // Declaration of a variable
		result = multiply(3, 4); // Calling multiply; function with constants 3 and 4 as input parameters
		// The result of the calculation is assigned to the result variable
		showResult(result); // Calling showResult function with result variable as input parameter
		cout << endl;
		getchar();
	}
	
	int multiply(int a, int b) // Definitions of the multiply and showResult functions
	{
		return a * b; // The result of the multiplication of variables a and b is the return value
	}
	void showResult(int result)
	{
		cout << "Result of the multiplication: " << result << endl; // No return value, only screen output
	}

## 2.9 Scope of variables
    #include <iostream>
	using namespace std;
	int a,b; // Declaration of global variables a and b
	void change() // Definition of change() function
	{
		int a; // Declaration of a local variable a
		a=0;
		{ // Second block
			int a=20; // Declaration of a local variable a
			cout << "The value of a within the second block is: " << a << endl;
		}
		cout << "The value of a within the change function is: " << a << endl;
	}
	int main() // Calling main function = program start
	{
		a=b=10; // The global variables a and b are assigned the value 10
		cout << "Before calling change function, the value of a is: " << a << " and b: " << b << endl;
		change(); // Calling change() function
		cout << "After calling change function, the value of a is: "<< a << " and b: " << b << endl;;
		system("pause");
		return 0;
	}

Screen output:

	Before calling change function, the value of a is: 10 and b: 10
	The value of a within the second block is 20
	The value of a within the change function is 0
	After calling change function, the value of a is: 10 and b: 10

All local variables defined inside a block are destroyed as soon as the block ends.	
Define variables **as local as possible** and as global as necessary. This is one of the basic rules of modular programming.

## 2.10 Inline function
A function can be declared as inline. This means that there is no actual function call. The validation of the syntax remains and the parameters are replaced accordingly.

It should be noted that the inline declaration is only suitable for functions with a short execution time compared to the effort required for the call.

	#include <cstdlib>
	#include <iostream>
	using namespace std;
	inline int maximum (int a, int b) {
	return a > b ? a : b;
	}
	int main()
	{
		cout << maximum(4,7) << endl;
		cout << maximum(3,9) << endl;
		system("pause");
		return 0;
	}
等价于：

	#include <cstdlib>
	#include <iostream>
	using namespace std;
	int main()
	{
		cout << (4 > 7 ? 4 : 7) << endl;
		cout << (3 > 9 ? 3 : 9) << endl;
		system("pause");
		return 0;
	}
 	
