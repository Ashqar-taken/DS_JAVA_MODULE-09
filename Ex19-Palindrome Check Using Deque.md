# Ex19 Palindrome Check Using Deque
## DATE: 20.07.2026
## AIM:
To design a program that checks whether a given message is a palindrome by removing all non-alphanumeric characters, converting all characters to lowercase, and using a deque data structure for comparison.

## Algorithm
1. Import the necessary Libraries.
2. Initialize a deque with the class ArrayDeque.
3. Obtain the string from the user.
4. Insert the string one character at a time into the deque uising addLast().
5. Use a while loop until the Deque is empty, poll from the front and from the last at the same time.
6. If the values are equal continue, else return false.

## Program:
```
/*
Program to checks whether a given message is a palindrome by removing all non-alphanumeric characters.
Developed by: Ashqar Ahamed S T
RegisterNumber: 212224240018
*/

import java.util.*;

public class PalindromeChecker {
    
    public static boolean isPalindrome(String message) {
        Deque<Character> deque = new ArrayDeque<>();
        
        for(int i=0;i<message.length();i++)
        {
            char ch = message.charAt(i);
            if(Character.isLetterOrDigit(ch))
            {
                ch = Character.toLowerCase(ch);
                deque.addLast(ch);
            }
        }
        
        while(deque.size() > 1)
        {
            char front = deque.pollFirst();
            char rear = deque.pollLast();
            
            if(front != rear)
            {
                return false;
            }
        }
        
        return true;
    }
    

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        //System.out.println("Enter a message:");
        String input = scanner.nextLine();

        if (isPalindrome(input)) {
            System.out.println("Palindrome");
        } else {
            System.out.println("Not a palindrome");
        }

        scanner.close();
    }
}

```

## Output:

<img width="751" height="267" alt="output Day4" src="https://github.com/user-attachments/assets/fff325cd-5644-415b-8ef7-0c67c4ac1c26" />


## Result:
The program successfully removes all non-alphanumeric characters, converts the text to lowercase, and uses a deque to efficiently compare characters from both ends. Hence, it determines whether the string is a palindrome.
