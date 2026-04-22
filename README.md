# JavaLabCS23.252
[1.Wap for addition sub mul div using object and classes.](#Program1)

[2.Write a class for addition of two distance where each distance is given in m,cm,mm.](#Program2)

[3.Test the result by creation of object in main class where each distance is given in m, cm](#Program3)

[4.Addition of  two time given in hours, minutes and seconds.](#Program4)

[5.Addition of two time given in hours, minutes .](#Program5)

[6.Collect the code from internet for any five programs of c language. (Fact, armstrong, palindrome, Fibonacci, pattern).](#Program6)

[7.Write a class that is having four method for 1-dimensional array. (Input, output 1,out2, reverse).).](#Program7)

[8.write a class with multiple methods to perform matrix operations (transpose, addition, sum of rows, sum of columns, sum of diagonal).](#Program8)

[9.Write a Java program using three classes to print 1–100, 1–100, 1–100 with and without thread and analyze the output. Also repeat the same program using Runnable interface.](#Program9)

[10. Using the concept of multithreading the output of all three threads must be synchronised (use join method).](#Program10)

[11. Addition of 2 numbers using swing.](#Program11)

[12.  Make a registration form with 10 elements and send the data into database (use jdbc connectivity)](#Program12)

[13.  Make one calculator in swing.](#Program13)

[14.  Matrix Addition using swing class.](#Program14)

[15.  Create one jframe apply 10 buttons on that after clicking on each button a new
structure is created.(Circle, oval rectangle, etc ....) ](#Program15)

[16.  Just using mouse Event create a frame like paint brush with selection of colour and width .](#Program16)

[17.  Create a package of any 5 classes of your choice and import it](#Program17)

[18.  Create one package and sub package  import and test it .](#Program18)

[19.  Create one small array of size 5 apply array out of bounds exception using try catch give a proper message in catch and demonstrate the exception exactly in the same fashion demonstrate arithmetic exception .](#Program19)

[20.  To test the range of age of one student.write a program using user defined exception.](#Program20)

[21.  File Handling Programs (given in the PPT)](#Program21)

[22.  Inheritance Programs, using interface and abstract classes.](#Program22)




## Program1

```
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
```

<img width="403" height="107" alt="image" src="https://github.com/user-attachments/assets/8b739f68-c8db-4793-9e60-42cd01003df1" />

## Program2

```

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
```
<img width="254" height="124" alt="image" src="https://github.com/user-attachments/assets/62dbe0eb-8b33-40f5-8447-cb809add0b09" />

## Program3
```
import java.util.Scanner;

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
}
```
<img width="252" height="117" alt="image" src="https://github.com/user-attachments/assets/aa742c40-4509-4ec6-bb7c-275edcc9fcd9" />

## Program4

```
import java.util.Scanner;

class TimeHMS {
    int hr, min, sec;

    void input() {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter hours: ");
        hr = sc.nextInt();
        System.out.print("Enter minutes: ");
        min = sc.nextInt();
        System.out.print("Enter seconds: ");
        sec = sc.nextInt();
    }

    TimeHMS add(TimeHMS t2) {
        TimeHMS t3 = new TimeHMS();

        t3.sec = this.sec + t2.sec;
        t3.min = this.min + t2.min;
        t3.hr = this.hr + t2.hr;

        if (t3.sec >= 60) {
            t3.min += t3.sec / 60;
            t3.sec = t3.sec % 60;
        }

        if (t3.min >= 60) {
            t3.hr += t3.min / 60;
            t3.min = t3.min % 60;
        }

        return t3;
    }

    void display() {
        System.out.println(hr + " hr " + min + " min " + sec + " sec");
    }

    public static void main(String[] args) {
        TimeHMS t1 = new TimeHMS();
        TimeHMS t2 = new TimeHMS();

        System.out.println("Enter first time:");
        t1.input();

        System.out.println("Enter second time:");
        t2.input();

        TimeHMS t3 = t1.add(t2);

        System.out.print("Total Time = ");
        t3.display();
    }
}
```
<img width="277" height="151" alt="image" src="https://github.com/user-attachments/assets/c73144e7-e15f-47e7-8630-ac50c4b27d0a" />

## Program5
```
import java.util.Scanner;

class TimeHM {
    int hr, min;

    void input() {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter hours: ");
        hr = sc.nextInt();
        System.out.print("Enter minutes: ");
        min = sc.nextInt();
    }

    TimeHM add(TimeHM t2) {
        TimeHM t3 = new TimeHM();

        t3.hr = this.hr + t2.hr;
        t3.min = this.min + t2.min;

        if (t3.min >= 60) {
            t3.hr += t3.min / 60;
            t3.min = t3.min % 60;
        }

        return t3;
    }

    void display() {
        System.out.println(hr + " hr " + min + " min");
    }

    public static void main(String[] args) {
        TimeHM t1 = new TimeHM();
        TimeHM t2 = new TimeHM();

        System.out.println("Enter first time:");
        t1.input();

        System.out.println("Enter second time:");
        t2.input();

        TimeHM t3 = t1.add(t2);

        System.out.print("Total Time = ");
        t3.display();
    }
}
 ```
<img width="242" height="122" alt="image" src="https://github.com/user-attachments/assets/abb867ba-751b-4698-84a4-cd4c01b301d5" />

## Program6
```
#include <stdio.h>

int main() {
    int n, i;
    long long fact = 1;

    printf("Enter a number: ");
    scanf("%d", &n);

    for(i = 1; i <= n; i++) {
        fact = fact * i;
    }

    printf("Factorial = %lld", fact);
    return 0;
}
```

<img width="151" height="45" alt="image" src="https://github.com/user-attachments/assets/6b0f5784-b187-467c-81bb-d8138af9cd08" />

```
#include <stdio.h>

int main() {
    int i, j, n;

    printf("Enter number of rows: ");
    scanf("%d", &n);

    for(i = 1; i <= n; i++) {
        for(j = 1; j <= i; j++) {
            printf("* ");
        }
        printf("\n");
    }

    return 0;
}
```
<img width="214" height="41" alt="image" src="https://github.com/user-attachments/assets/eff13d7c-7f67-4360-b5af-a036fac0c79a" />

```
#include <stdio.h>

int main() {
    int n, temp, rem, rev = 0;

    printf("Enter a number: ");
    scanf("%d", &n);

    temp = n;
    while(temp > 0) {
        rem = temp % 10;
        rev = rev * 10 + rem;
        temp /= 10;
    }

    if(rev == n)
        printf("Palindrome Number");
    else
        printf("Not a Palindrome Number");

    return 0;
}
```

<img width="185" height="40" alt="image" src="https://github.com/user-attachments/assets/245bc35f-b4f9-4b80-b1e3-93c24a1ff5ef" />

```
#include <stdio.h>

int main() {
    int n, i;
    int a = 0, b = 1, c;

    printf("Enter number of terms: ");
    scanf("%d", &n);

    printf("Fibonacci Series: ");
    for(i = 1; i <= n; i++) {
        printf("%d ", a);
        c = a + b;
        a = b;
        b = c;
    }

    return 0;
}
```

<img width="281" height="34" alt="image" src="https://github.com/user-attachments/assets/fb0e4d7f-283b-4236-a655-af75efd30cfb" />


```
#include <stdio.h>

int main() {
    int i, j, n;

    printf("Enter number of rows: ");
    scanf("%d", &n);

    for(i = 1; i <= n; i++) {
        for(j = 1; j <= i; j++) {
            printf("* ");
        }
        printf("\n");
    }

    return 0;
}
```
<img width="255" height="109" alt="image" src="https://github.com/user-attachments/assets/dfa67ea2-7635-46be-bd6b-619a9ad32f6d" />

## program7

```
import java.util.Scanner;

class Array1D {
    int a[] = new int[100];
    int n;

    void input() {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter size of array: ");
        n = sc.nextInt();

        System.out.println("Enter array elements:");
        for (int i = 0; i < n; i++) {
            a[i] = sc.nextInt();
        }
    }

    void output1() {
        System.out.println("Array elements are:");
        for (int i = 0; i < n; i++) {
            System.out.print(a[i] + " ");
        }
        System.out.println();
    }

    void output2() {
        System.out.println("Array elements with index:");
        for (int i = 0; i < n; i++) {
            System.out.println("a[" + i + "] = " + a[i]);
        }
    }

    void reverse() {
        System.out.println("Array in reverse order:");
        for (int i = n - 1; i >= 0; i--) {
            System.out.print(a[i] + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        Array1D obj = new Array1D();
        obj.input();
        obj.output1();
        obj.output2();
        obj.reverse();
    }
}
```

<img width="391" height="258" alt="image" src="https://github.com/user-attachments/assets/20da65e4-ec24-438f-a3c0-a45d9191f632" />

## Program8

```
import java.util.Scanner;

class MatrixOperation {
    int a[][] = new int[10][10];
    int b[][] = new int[10][10];
    int c[][] = new int[10][10];
    int r, col;

    void inputMatrices() {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter rows: ");
        r = sc.nextInt();
        System.out.print("Enter columns: ");
        col = sc.nextInt();

        System.out.println("Enter first matrix:");
        for (int i = 0; i < r; i++) {
            for (int j = 0; j < col; j++) {
                a[i][j] = sc.nextInt();
            }
        }

        System.out.println("Enter second matrix:");
        for (int i = 0; i < r; i++) {
            for (int j = 0; j < col; j++) {
                b[i][j] = sc.nextInt();
            }
        }
    }

    void displayMatrix(int m[][]) {
        for (int i = 0; i < r; i++) {
            for (int j = 0; j < col; j++) {
                System.out.print(m[i][j] + " ");
            }
            System.out.println();
        }
    }

    void addition() {
        System.out.println("Addition of matrices:");
        for (int i = 0; i < r; i++) {
            for (int j = 0; j < col; j++) {
                c[i][j] = a[i][j] + b[i][j];
                System.out.print(c[i][j] + " ");
            }
            System.out.println();
        }
    }

    void transpose() {
        System.out.println("Transpose of first matrix:");
        for (int i = 0; i < col; i++) {
            for (int j = 0; j < r; j++) {
                System.out.print(a[j][i] + " ");
            }
            System.out.println();
        }
    }

    void sumOfRows() {
        System.out.println("Sum of rows of first matrix:");
        for (int i = 0; i < r; i++) {
            int sum = 0;
            for (int j = 0; j < col; j++) {
                sum += a[i][j];
            }
            System.out.println("Row " + (i + 1) + " sum = " + sum);
        }
    }

    void sumOfColumns() {
        System.out.println("Sum of columns of first matrix:");
        for (int j = 0; j < col; j++) {
            int sum = 0;
            for (int i = 0; i < r; i++) {
                sum += a[i][j];
            }
            System.out.println("Column " + (j + 1) + " sum = " + sum);
        }
    }

    void sumOfDiagonal() {
        if (r == col) {
            int sum = 0;
            for (int i = 0; i < r; i++) {
                sum += a[i][i];
            }
            System.out.println("Sum of diagonal elements = " + sum);
        } else {
            System.out.println("Diagonal sum possible only for square matrix");
        }
    }

    public static void main(String[] args) {
        MatrixOperation obj = new MatrixOperation();
        obj.inputMatrices();

        System.out.println("First Matrix:");
        obj.displayMatrix(obj.a);

        System.out.println("Second Matrix:");
        obj.displayMatrix(obj.b);

        obj.addition();
        obj.transpose();
        obj.sumOfRows();
        obj.sumOfColumns();
        obj.sumOfDiagonal();
    }
}
```

<img width="317" height="521" alt="image" src="https://github.com/user-attachments/assets/ffd36f7f-aa35-48f2-9b87-5bd9551cd047" />

## Program9

```
class NumberThread1 extends Thread {
    public void run() {
        for (int i = 1; i <= 100; i++) {
            System.out.println("Thread 1: " + i);
        }
    }
}

class NumberThread2 extends Thread {
    public void run() {
        for (int i = 1; i <= 100; i++) {
            System.out.println("Thread 2: " + i);
        }
    }
}

class NumberThread3 extends Thread {
    public void run() {
        for (int i = 1; i <= 100; i++) {
            System.out.println("Thread 3: " + i);
        }
    }
}

class Runnable1 implements Runnable {
    public void run() {
        for (int i = 1; i <= 100; i++) {
            System.out.println("Runnable 1: " + i);
        }
    }
}

class Runnable2 implements Runnable {
    public void run() {
        for (int i = 1; i <= 100; i++) {
            System.out.println("Runnable 2: " + i);
        }
    }
}

class Runnable3 implements Runnable {
    public void run() {
        for (int i = 1; i <= 100; i++) {
            System.out.println("Runnable 3: " + i);
        }
    }
}

public class Program9 {
    public static void main(String[] args) {
        System.out.println("WITHOUT THREAD:");
        for (int i = 1; i <= 100; i++) {
            System.out.print("Class 1: " + i+" ");
        }
        for (int i = 1; i <= 100; i++) {
            System.out.print("Class 2: " + i+" ");
        }
        for (int i = 1; i <= 100; i++) {
            System.out.print("Class 3: " + i +" ");
        }

        System.out.println("\nUSING THREAD CLASS:");
        NumberThread1 t1 = new NumberThread1();
        NumberThread2 t2 = new NumberThread2();
        NumberThread3 t3 = new NumberThread3();

        t1.start();
        t2.start();
        t3.start();

        try {
            t1.join();
            t2.join();
            t3.join();
        } catch (Exception e) {
            System.out.println(e);
        }

        System.out.println("\nUSING RUNNABLE INTERFACE:");
        Thread r1 = new Thread(new Runnable1());
        Thread r2 = new Thread(new Runnable2());
        Thread r3 = new Thread(new Runnable3());

        r1.start();
        r2.start();
        r3.start();
    }
}
```

<img width="160" height="612" alt="image" src="https://github.com/user-attachments/assets/78dc3189-d2c1-42a8-910a-128177895e90" />



