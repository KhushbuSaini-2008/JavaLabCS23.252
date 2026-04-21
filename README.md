# JavaLabCS23.252
1.[Wap for addition sub mul div using object and classes.](#Program1)
2.[Write a class for addition of two distance where each distance is given in m,cm,mm.](#Program2)
3.[Test the result by creation of object in main class where each distance is given in m, cm](#Program3)
4.[Addition of time given in hours, minutes and seconds.](#Program4)
```import java.util.Scanner;

## Program1
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

## Program2
```import java.util.Scanner;

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
<img width="299" height="133" alt="image" src="https://github.com/user-attachments/assets/e08c9287-e197-4398-bab0-f8a04f803095" />```



