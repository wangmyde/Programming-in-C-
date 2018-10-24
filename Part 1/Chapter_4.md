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
>> C-style strings: single-dimensional arrays of characters (char-variables)  
>> C++-strings: string class from the standard library


