# Control Structures
### 1 if statement
Syntax:

    if(condition) {
        statement;
    }

    == equal
    <= is less than (or equal to)
    >= is greater than (or equal to)
    < is less than
    > is greater than
    != is unequal
    
    if (x == 20) {
        cout << "The number entered is 20." << endl;
    }
    else if (x <= 19) {
        cout << "The number entered is less than or equal to 19." << endl;
    else {
        cout << "The number entered is greater than 20." << endl;
    }
    
    int i = 10, j = 20;
    if ((i == 10) && (j == 10))
    {
        cout << "Both values are equal to ten" << endl;
    }
    else if ((i == 10) || (j == 10))
    {
        cout << "One value or both values are equal to ten " << endl;
    }
    else if ((i != 10) && !(j == 10))
    {
        cout << "Both values are unequal to ten " << endl;
    }
    
### 2 Conditional expression
syntax:
`Value = Condition ("Question") ? Expression for TRUE : Expression for FALSE;`
In the above example: Is a less than b? If true (i.e. a is less than), then assign a to min, if false (i.e.
b is less than), then assign b to min.

### 3 Switch statement
Syntax:
    switch(AboveSpeedLimit) {
        case 0 : {
        Penalty = 0;
        break;
        }
        case 10 : {
        Penalty = 20;
        break;
        }
        case 15 : {
        Penalty = 50;
        break;
        }
        case 20 :
        case 25 :
        case 30 : {
        Penalty = AboveSpeedLimit * 10;
       break;
       }
       default : {
       Penalty = Subpoena();
       PenaltyDegree = Verdict();
       }
    }  
The default case is executed if none of the cases is true.    
 
### 4 for Loops
Syntax:

    for (init; condition; increment) {
        statement;
    }

### 5 while loops
Syntax:

    while (condition) {
        statement;
    }
  
### 6 do-while loops
Syntax:
    do{
        statement;
    }
    while (condition)
The do-while loop checks its condition at the end of the loop (unlike for and while loops which test the condition at the beginning of the loop).
