# JavaLabCS23.252
1.[Wap for addition sub mul div using object and classes.](#Program1)
2.[Write a class for addition of two distance where each distance is given in m,cm,mm.](#Program2)
3.[Test the result by creation of object in main class where each distance is given in m, cm](#Program3)
4.[Addition of time given in hours, minutes and seconds.](#Program4)
## Program 1

```java
import java.util.Scanner;

public class Main {
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
}
<img width="281" height="121" alt="image" src="https://github.com/user-attachments/assets/b7a732b6-d55a-4d93-848a-0d16f5941e9f" />```


## Program 2

```java
import java.util.Scanner;

class Distance {
    int m, cm, mm;

    void input() {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter meter: ");
        m = sc.nextInt();
        System.out.print("Enter centimeter: ");
        cm = sc.nextInt();
        System.out.print("Enter millimeter: ");
        mm = sc.nextInt();
    }

    void display() {
        System.out.println(m + " m " + cm + " cm " + mm + " mm");
    }

    Distance add(Distance d2) {
        Distance d3 = new Distance();

        d3.mm = this.mm + d2.mm;
        d3.cm = this.cm + d2.cm;
        d3.m = this.m + d2.m;

        if (d3.mm >= 10) {
            d3.cm += d3.mm / 10;
            d3.mm = d3.mm % 10;
        }

        if (d3.cm >= 100) {
            d3.m += d3.cm / 100;
            d3.cm = d3.cm % 100;
        }

        return d3;
    }

    public static void main(String[] args) {
        Distance d1 = new Distance();
        Distance d2 = new Distance();

        System.out.println("Enter first distance:");
        d1.input();

        System.out.println("Enter second distance:");
        d2.input();

        Distance d3 = d1.add(d2);

        System.out.print("Total Distance = ");
        d3.display();
    }
}
<img width="254" height="124" alt="image" src="https://github.com/user-attachments/assets/62dbe0eb-8b33-40f5-8447-cb809add0b09" />```




