# Ex16 Check for Balanced Parentheses Using Stack
## DATE: 16.07.2026
## AIM:
To write a Java program that verifies whether the parentheses (brackets) in an input string are balanced — meaning each opening bracket (, {, [ has a corresponding and correctly ordered closing bracket ), }, ].

## Algorithm
1. Import the necessary libraries.
2. Define the required methods to implement stack such as push, pop, peek and display.
3. Initialize the stack and insert if the given value is open brackets.
4. If the given value is closed bracket, pop the stack check if the open bracket poped is the respective open bracket
5. If not return false else repeat until all the values are passed.

## Program:
```
/*
Program to verify whether the parentheses (brackets) in an input string are balanced
Developed by: Ashqar Ahamed S T
RegisterNumber: 212224240018
*/

import java.util.Scanner;

class ArrayStack
{
    private char[] stack;
    private int top;
    private int capacity;
    
    public ArrayStack(int capacity)
    {
        this.capacity = capacity;
        stack = new char[capacity];
        top = -1;
    }
    
    public void push(char c)
    {
        if( top >= capacity)
        {
            System.out.println("Stack Overflow");
        
        }
        else
            stack[++top] = c;
    }
    
    public char pop()
    {
        return stack[top--];
    }
    
    public boolean isEmpty()
    {
        return top == -1;
    }
}
public class ParenChecker {
    
    

    // Checks if expr has balanced brackets
    public static boolean isBalanced(String expr) {
        ArrayStack st = new ArrayStack(expr.length());
        for (char ch : expr.toCharArray()) {
            if (ch == '(' || ch == '{' || ch == '[') {
                st.push(ch);
            } else if (ch == ')' || ch == '}' || ch == ']') {
                if (st.isEmpty()) return false;
                char top = st.pop();
                if ((ch == ')' && top != '(') ||
                    (ch == '}' && top != '{') ||
                    (ch == ']' && top != '[')) {
                    return false;
                }
            }
        }
        return st.isEmpty();
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String expr = sc.nextLine();
        boolean ok = isBalanced(expr);
        System.out.println(ok);
        sc.close();
    }
}

```

## Output:

<img width="625" height="278" alt="output Day1" src="https://github.com/user-attachments/assets/c3f8e54f-940f-43d2-8604-f4ae4521e5de" />


## Result:
Thus,the program correctly checks whether an input string has balanced parentheses using a stack.
