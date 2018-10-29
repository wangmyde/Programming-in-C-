### 1 Declaration
```
class ACCOUNT // Declaration of the ACCOUNT class
{
public:
int ACCOUNTBALANCE;
};
```
### 2. Definition
We can then use it like any other data type and build variables (instances) in the main program.
```
ACCOUNT TESTACCOUNT; // Creating an instance of the ACCOUNT class
```
### 3 Access
You access an instance by using its name together with the name of the element, separated by the member access operator `.`(for accessing the elements of an object).
```
TESTACCOUNT.ACCOUNTBALANCE = 1000; // Sets the ACCOUNTBALANCE of TESTACCOUNT to 100
```
### 4 Name
The header file's name == the class name
### 5 Private und Public
> Private: You can no longer access the data members and data member values of this class "from the outside" of the class  
```
class ACCOUNT // Definition of the ACCOUNT class
{
    int ACCOUNTNUMBER;
};
int main()
{
    ACCOUNT CurrentAccount; // Instantiated current account
    CurrentAccount. ACCOUNTNUMBER =555666; // Compiler error!!!
}
```
The direct access to the data member values of a class, as specified in the above example, leads to an **error** message such as "ACCOUNT::ACCOUNTNUMBER is not accessible" when compiling!

The default setting for the declaration of class data members should therefore be **"private"**.
> Public
```
class ACCOUNT // Definition of the ACCOUNT class
{
    public: int ACCOUNTNUMBER;
};
int main()
{
    ACCOUNT CurrentAccount; // Instantiated current account
    CurrentAccount. ACCOUNTNUMBER =555666; // Access the instance
}
```
This way the compiler will no longer generate an error message.

Each class contains a public section (public) that can be accessed from the outside of the class. The private section (private) is only meant for the internal use within the class. A well-defined class should not take things that the user does not need to know into the public sphere.

### 5 Member functions of a class in C++
Member functions are functions that belong to a particular class.

Member functions are able to access private members of a class.

The validity range of member functions is the class; outside the class they do not exist. They can only be called within the class or by an instance of the class. You can use the member functions to access all data members of the class, regardless of their respective access restrictions. Member functions can also be declared as public, protected and private.
```
#include <iostream>
#include <cstdlib>
using namespace std;
class Sound
{
    private:
    int timer;
    void setTimer(int t) { timer = t; };
    public:
    void Open() { setTimer (0); };
    void Play() { };
    void Record() { };
    void Safe() { };
    void FastForward() { };
};
int main()
{
    Sound k;
    k.Open(); // possible
    // k.setTimer (0); // not possible
    system("pause");
    return 0;
}
```
The public member functions of the class should include functions such as:
`Open(), Play(), Record(), Safe(), FastForward()`

The private member functions are used for the internal work of the class. They are not intended to be used by the user.

### 6 Declaration of member functions
In C++, a member function must first be `declared` and `defined` before it can be used.

Member functions can be declared as `public`, `private` or `protected`.

The member function is defined in the `function header` and `function body`.
```
class ACCOUNT
{
    private:
    int ACCOUNTBALANCE; // Declaration of a data member
    public: // Definition of the member function READ_ACCOUNTBALANCE
    int READ_ACCOUNTBALANCE ()
    {
        return(ACCOUNTBALANCE);
    }
};
```
Member functions can be defined inside or outside the class.
> Definition within the class
```
class ACCOUNT
{
    private:
    int ACCOUNTBALANCE; // Declaration of a data member
    public: // Definition of the member function READ_ACCOUNTBALANCE
    int READ_ACCOUNTBALANCE ()
    {
        return(ACCOUNTBALANCE);
    }
};
```
> Definition outside the class
For more extensive member functions, the definition within the class becomes too confusing and should therefore take place outside the class declaration.
Please note that in this case the class operator `::` must be used.
```
member function header: int ACCOUNT:: READ_ACCOUNTBALANCE ()
member function body: { return (ACCOUNTBALANCE);}
```

### 7 friend
In C++, it is possible to make private or protected data members or member functions accessible to other classes by declaring them as `friend`.
```
class TESTCLASS
{
    friend class FRIENDCLASS; // friend-declaration
    private: // Declaration of data members and member functions of class TESTCLASS
    …
};
```
This allows all objects of class “FRIENDCLASS” to access the private members of class “TESTCLASS”.
Note: “Friends" of a class have the same access rights as the members of the class itself.

### 8 Calling a member function
```
TESTACCOUNT.READ_ACCOUNTBALANCE(); 
```
### 9 Example
```
class ACCOUNT
{
    private:
    int ACCOUNTBALANCE;
    public:
    bool CHANGE_BALANCE (int);
    int READ_ACCOUNTBALANCE();
};
bool ACCOUNT::CHANGE_BALANCE(int INPUT) // Definition of the member function "CHANGE_BALANCE"
{
    if((INPUT>=0)&&(INPUT<=100000)) // The entered value must be between 0 and 100000
    {
        ACCOUNTBALANCE=INPUT; // ACCOUNTBALANCE is changed
        return(1); // Change is made
    }
    return(0); // Change failed (e.g. when entering a negative value)
int ACCOUNT::READ_ACCOUNTBALANCE() // Definition of member function "READ_ACCOUNTBALANCE"
   {return(ACCOUNTBALANCE);}
```
