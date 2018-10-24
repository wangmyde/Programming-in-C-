### 1 Arrays
Syntax: 
`type name[arraySize]`;
The size of the array **cannot** be changed by a variable or later in the program/source code.

    int myArray[5];
    myArray [0] = -200;
    myArray [1] = -100;
    myArray [2] = 0;
    myArray [3] = 100;
    myArray [4] = 200;
Since each integer value occupies a memory space of 4 bytes, the array requires a total of 20 bytes.
Arrays in C++ have **0** as the index of their first element that is also called base index.

    int result = myArray [3] + myArray [4]; // The result is 300
    
    int myArray [5] = { -200, -100, 0, 100, 200 };
    
If you know exactly how many elements your array stores, and if you fill up the array when declaring it, you can omit the array size when declaring the array. 

    int myArray[] = { -200, -100, 0, 100, 200 };

    srand(time(NULL)); // Re-generate random numbers based on the time
    lottery [i] = rand() % 49 + 1; // Random number between 1 and 49
    
    int x = 10;
    int myArray[x]; // Compiler error
It **cannot** use a variable to declare the size of an array.

Arrays that have been allocated in the heap memory can use a variable to declare the array
size:

    int x = 10;
    int myArray[x] = new int[x]; // this is OK (also part of the second part of the course)
    
### 2 Multi-dimensional arrays
    int table[2][3]={{10,11,12},{2,3,4}}; // Array with 2 rows and 3 columns
    
### 3 Strings (Character strings)
C++ has two types of strings:
> C-style strings: single-dimensional arrays of characters (char-variables)  
> C++-strings: string class from the standard library
1. C-Strings
The `char` data type is used for a single character.

    char character = 'A';
Make sure that the A is written in single quotes. The compiler literally does not write the character A into the variable, but the character code of the character in the ASCII table.  

**Note**: A character within single quotes is considered as a value.

In C++ programs, strings are represented by arrays of the char data type. Note that a string is written in **double** quotes.

    char text[] = "This is a string.";
With this you reserve 18 bytes of memory and store the string in this memory area. The reason why there are 18 bytes reserved is that there is a null character at the end of each
string and C/C++ takes this fact into account by leaving space for the null-terminating character in the memory allocation. The null-terminating character is a special character represented by `\0`.在屏幕上显示位nothing.若把某一为改为'\0',则string会在那一位结束，如下：

    #include <iostream>
    #include <cstdlib>
    using namespace std;
    int main()
    {
        char str[] = "This is a string.";
        cout << str << endl;
        str[7] = '\0'; // Single quotes !
        cout << str << endl;
        cout << endl << "Press any key to continue...";
        system("pause");
     }

2. C++ Strings
In C++ the string class is defined in the header file <string>:
    
    #include <string>
    using namespace std;
    string str1; // empty string
    string str2 = „I am a string“;
    string str3(10, ‚+’); // Variable str3 holds the value 10 plus sign
    string str4(str2,2,4); // Variable str4 holds the value: am a
    string str5 = str2 + “for testing purposes“; // Variable str5 holds the value: I am a string for testing purposes
    
    
    
