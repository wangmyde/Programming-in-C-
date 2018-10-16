## 1.1 Making a C++ program executable
To create and execute a C++ program, basically the same steps are necessary as in C:
> The program is created using an editor  
> The program is compiled  
> The linker finally creates the executable file.

## 1.2 Editor
An editor is used to create the text files that contain the C++ code. There are two different types of files:
> Source files: contain definitions of global variables and functions. Each C++ program consists of **at least one** source file.
>> The most common extensions for source files are `.cpp` and `.cc`.
> Header files: provide the information needed in various source files.
>> The most common extensions for header files are `.h`, `.hpp` or nothing.

## 1.3 Compilers
1. A translation unit = a source file + the included header files
2. The compiler generates an object file (also called module) from each translation unit.
3. The object file contains the machine code

## 1.4 Linker
The linker combines object files into an executable file.
object files here include:
1. the self-generated object files
2. the startup-code
3. the modules with the used functions and classes of the standard library

## 1.5 Libraries
In C/C++ there are libraries that contain different classes and functions.
The functions from the library files required for the program are already bound to it during the linking phase. The use of libraries is done in two steps. 
> First, the header file must be included into the source code file using the #include pre-processor command.   
> In the second step, the linker gets to know the actual library files, for example <string>.
  
## 1.6 endl
    cout << "Hello C++-friends!" << endl;
or: 

    cout << "Hello C++- friends!";
    cout << endl;
or: 

    cout<< "Hello C++- friends!\n";

  
