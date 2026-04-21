# JavaLabCS23.252
1.[Wap for addition sub mul div using object and classes.](#Program1)
2.[Write a class for addition of two distance where each distance is given in m,cm,mm.](#Program2)
3.[Test the result by creation of object in main class where each distance is given in m, cm](#Program3)
4.[Wap for addition sub mul div using object and classes.](#Program4)
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
    int meter, cm, mm;

    // Method to input distance
    void input() {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter meter: ");
        meter = sc.nextInt();
        System.out.print("Enter centimeter: ");
        cm = sc.nextInt();
        System.out.print("Enter millimeter: ");
        mm = sc.nextInt();
    }

    // Method to display distance
    void display() {
        System.out.println(meter + " m " + cm + " cm " + mm + " mm");
    }

    // Method to add two distances
    static Distance add(Distance d1, Distance d2) {
        Distance d3 = new Distance();

        d3.mm = d1.mm + d2.mm;
        d3.cm = d1.cm + d2.cm;
        d3.meter = d1.meter + d2.meter;

        // Convert mm to cm
        if (d3.mm >= 10) {
            d3.cm += d3.mm / 10;
            d3.mm = d3.mm % 10;
        }

        // Convert cm to meter
        if (d3.cm >= 100) {
            d3.meter += d3.cm / 100;
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

        Distance result = add(d1, d2);

        System.out.print("Total Distance: ");
        result.display();
    }
}```
Output:
<img width="380" height="124" alt="image" src="https://github.com/user-attachments/assets/b68815ba-073b-4381-97ff-41dc266f92a6" />
## Program3
```import java.util.Scanner;

class DistanceMC {
    int m, cm;

    void input() {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter meter: ");
        m = sc.nextInt();
        System.out.print("Enter centimeter: ");
        cm = sc.nextInt();
    }

    DistanceMC add(DistanceMC d2) {
        DistanceMC d3 = new DistanceMC();
        d3.m = this.m + d2.m;
        d3.cm = this.cm + d2.cm;

        if (d3.cm >= 100) {
            d3.m += d3.cm / 100;
            d3.cm = d3.cm % 100;
        }
        return d3;
    }

    void display() {
        System.out.println(m + " m " + cm + " cm");
    }
}

public class MainClass {
    public static void main(String[] args) {
        DistanceMC d1 = new DistanceMC();
        DistanceMC d2 = new DistanceMC();

        System.out.println("Enter first distance:");
        d1.input();

        System.out.println("Enter second distance:");
        d2.input();

        DistanceMC d3 = d1.add(d2);

        System.out.print("Total Distance = ");
        d3.display();
    }
}```
