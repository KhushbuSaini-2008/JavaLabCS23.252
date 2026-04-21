# JavaLabCS23.252
(write a java add to number)[#xyz]
```import java.util.Scanner;

###xyz
public class main{
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        // Taking input
        System.out.print("Enter first number: ");
        int num1 = sc.nextInt();

        System.out.print("Enter second number: ");
        int num2 = sc.nextInt();

        // Performing operations directly
        int addition = num1 + num2;
        int subtraction = num1 - num2;
        int multiplication = num1 * num2;

        double division;
        if (num2 != 0) {
            division = (double) num1 / num2;
        } else {
            System.out.println("Division by zero is not allowed.");
            division = 0;
        }

        // Displaying results
        System.out.println("\nAddition: " + addition);
        System.out.println("Subtraction: " + subtraction);
        System.out.println("Multiplication: " + multiplication);
        System.out.println("Division: " + division);

        sc.close();
    }
}```
OUTPUT:
Enter first number: 55
Enter second number: 10

Addition: 65
Subtraction: 45
Multiplication: 550
Division: 5.5
