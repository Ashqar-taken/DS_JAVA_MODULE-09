# Ex18 Simulation of a Ticket Counter Using Queue (Linked List Implementation)
## DATE: 18.08.2026
## AIM:
To simulate the functioning of a ticket counter that operates on a First-In-First-Out (FIFO) basis using a queue implemented via a linked list in Java.
## Algorithm
1. Import the necessary Libraries.
2. Define the required methods to implement a queue data structure such as enqueue, dequeue.
3. Initialize a Queue and perform the operations given by the user.
4. Use a switch case to identify the given operation and perform them by calling the methods.
5. Simulate a Ticket Counter.

## Program:
```
/*
Program to functioning of a ticket counter that operates on a First-In-First-Out (FIFO)
Developed by: Ashqar Ahamed S T
RegisterNumber: 21224240018
*/

import java.util.Scanner;

class Node {
    String customerName;
    Node next;

    public Node(String name) {
        this.customerName = name;
        this.next = null;
    }
}

class TicketQueue {
    private Node front;
    private Node rear;

    public TicketQueue() {
        this.front = this.rear = null;
    }

    public void enqueue(String customerName) {
        Node new_node = new Node(customerName);
        
        if(front == null && rear == null)
        {
            front = rear = new_node;
        }
        else
        {
            rear.next = new_node;
            rear = new_node;
        }
    }

    public void dequeue() {
        if(rear==null)
        {
            System.out.println("Queue is empty. No customer to serve.");
            return;
        }
        System.out.println("Serving customer: " + front.customerName);
        if(front == rear)
        {
            front = rear = null;
        }
        else
        {
            front = front.next;
        }
    }

    public void displayQueue() {
        Node temp = front;
        if(rear == null)
        {
            System.out.println("Queue is empty.");
            return;
        }
        System.out.print("Queue: ");
        while(temp!=null)
        {
            System.out.print(temp.customerName);
            if(temp.next!=null)
            {
                System.out.print(" -> ");
            }
            temp = temp.next;
        }
        System.out.println();
        
        
    }
}

public class TicketCounter {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        TicketQueue queue = new TicketQueue();
        String command;

        //System.out.println("Ticket Counter Simulation");
        //System.out.println("Commands: enqueue <name>, dequeue, display, exit");

        while (true) {
            //System.out.print("Enter command: ");

            // Fix for NoSuchElementException
            if (!scanner.hasNextLine()) {
                //System.out.println("No more input. Exiting simulation.");
                break;
            }

            command = scanner.nextLine().trim();
            if (command.isEmpty()) continue;

            String[] parts = command.split(" ");

            switch (parts[0]) {
                case "enqueue":
                    if (parts.length >= 2) {
                        queue.enqueue(parts[1]);
                    }
                    break;
                case "dequeue":
                    queue.dequeue();
                    break;
                case "display":
                    queue.displayQueue();
                    break;
                case "exit":
                    System.out.println("Exiting simulation.");
                    scanner.close();
                    return;
                default:
                    System.out.println("Invalid command.");
            }
        }

        scanner.close(); // Safe close
    }
}

```

## Output:

<img width="1247" height="792" alt="output Day3" src="https://github.com/user-attachments/assets/fc4a9a04-28d1-4dd9-bc10-a391695e9ca9" />


## Result:
Thus, the program successfully simulates a ticket counter queue where customers are served in FIFO order using a linked list-based queue implementation.
