# DSA-Assignment-2
//QUESTION #1:
import java.util.Scanner;

class Stack {
    int top;
    int size;
    int[] stack;

    
    Stack(int size) {
        this.size = size;
        stack = new int[size];
        top = -1;
    }

    
    void push(int value) {
        if (top == size - 1) {
            System.out.println("Stack Overflow!");
        } else {
            top++;
            stack[top] = value;
            System.out.println(value + " pushed into stack.");
        }
    }

   
    void pop() {
        if (top == -1) {
            System.out.println("Stack Underflow!");
        } else {
            System.out.println("Popped element: " + stack[top]);
            top--;
        }
    }

   
    void peek() {
        if (top == -1) {
            System.out.println("Stack is Empty!");
        } else {
            System.out.println("Top element: " + stack[top]);
        }
    }


    void display() {
        if (top == -1) {
            System.out.println("Stack is Empty!");
        } else {
            System.out.println("Stack elements:");
            for (int i = top; i >= 0; i--) {
                System.out.println(stack[i]);
            }
        }
    }
}

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter stack size: ");
        int n = sc.nextInt();

        Stack s = new Stack(n);

        int choice;

        do {
            System.out.println("\n--- STACK MENU ---");
            System.out.println("1. Push");
            System.out.println("2. Pop");
            System.out.println("3. Peek");
            System.out.println("4. Display");
            System.out.println("5. Exit");

            System.out.print("Enter your choice: ");
            choice = sc.nextInt();

            switch (choice) {
                case 1:
                    System.out.print("Enter element: ");
                    int value = sc.nextInt();
                    s.push(value);
                    break;

                case 2:
                    s.pop();
                    break;

                case 3:
                    s.peek();
                    break;

                case 4:
                    s.display();
                    break;

                case 5:
                    System.out.println("Program Ended.");
                    break;

                default:
                    System.out.println("Invalid Choice!");
            }

        } while (choice != 5);

        sc.close();
    }
}

//QUESTION #2
Final Answer:
.Final Stack
.Final contents: 10, 20

.Top element: 20

.Bottom element: 10

.Stack size: 2
Question #3
import java.util.Scanner;

class Queue {
    int front, rear, size;
    int[] queue;

    // Constructor
    Queue(int size) {
        this.size = size;
        queue = new int[size];
        front = -1;
        rear = -1;
    }

    // Enqueue operation
    void enqueue(int value) {
        if (rear == size - 1) {
            System.out.println("Queue Overflow!");
        } else {
            if (front == -1) {
                front = 0;
            }
            rear++;
            queue[rear] = value;
            System.out.println(value + " inserted into Queue.");
        }
    }

    // Dequeue operation
    void dequeue() {
        if (front == -1 || front > rear) {
            System.out.println("Queue Underflow!");
        } else {
            System.out.println("Deleted element: " + queue[front]);
            front++;

            if (front > rear) {
                front = -1;
                rear = -1;
            }
        }
    }

    // Front operation
    void showFront() {
        if (front == -1) {
            System.out.println("Queue is Empty!");
        } else {
            System.out.println("Front element: " + queue[front]);
        }
    }

    // Display operation
    void display() {
        if (front == -1) {
            System.out.println("Queue is Empty!");
        } else {
            System.out.println("Queue elements:");
            for (int i = front; i <= rear; i++) {
                System.out.println(queue[i]);
            }
        }
    }
}

public class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Queue size: ");
        int n = sc.nextInt();

        Queue q = new Queue(n);

        int choice;

        do {
            System.out.println("\n--- QUEUE MENU ---");
            System.out.println("1. Enqueue");
            System.out.println("2. Dequeue");
            System.out.println("3. Front");
            System.out.println("4. Display");
            System.out.println("5. Exit");

            System.out.print("Enter your choice: ");
            choice = sc.nextInt();

            switch (choice) {
                case 1:
                    System.out.print("Enter element: ");
                    int value = sc.nextInt();
                    q.enqueue(value);
                    break;

                case 2:
                    q.dequeue();
                    break;

                case 3:
                    q.showFront();
                    break;

                case 4:
                    q.display();
                    break;

                case 5:
                    System.out.println("Program Ended.");
                    break;

                default:
                    System.out.println("Invalid Choice!");
            }

        } while (choice != 5);

        sc.close();
    }
}
Question #4
Final contents: 30, 40

Front element: 30

Rear element: 40

Queue size: 2