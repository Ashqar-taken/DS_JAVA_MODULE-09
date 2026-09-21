# Ex17 Reversing a String Using Stack Data Structure
## DATE: 17.07.2026
## AIM:
To write a Java program that reverses an input string using a stack, without using built-in reverse functions.

## Algorithm
1. Import the utilities.
2. Initialize a stack using the "Stack" class.
3. Obtain the string from the user.
4. Push each character into stack.
5. Once all the character are pushed, Pop the stack until the stack is empty.
6. Use a string Builder the convert the popped character into String.
7. Display the popped string result.

## Program:
```
/*
Program to reverses an input string using a stack
Developed by: Ashqar Ahamed S T
RegisterNumber: 212224240018
*/

import java.util.Scanner;
import java.util.Stack;

public class ReverseStringWithStack {

    public static String reverseString(String input) {
        
        Stack<Character> stack = new Stack<>();
        for(char c : input.toCharArray())
        {
            stack.push(c);
        }
        
        StringBuilder result = new StringBuilder();
        while(!stack.isEmpty())
        {
            result.append(stack.pop());
        }
        
        return result.toString();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();

        // Reverse using stack
        String reversed = reverseString(input);

        // Display result
        System.out.println(reversed);

        scanner.close();
    }
}

```

## Output:

<img width="647" height="247" alt="output Day2" src="https://github.com/user-attachments/assets/9483e18a-f5a9-4d1f-b6d5-561058acbe29" />


## Result:
Thus, the program successfully reverses the given string using a stack without relying on built-in reverse functions.
