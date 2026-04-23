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

[13.Write a Java Swing program to create a simple calculator that performs addition, subtraction, multiplication, and division of two numbers.](#Program13)

[14.Write a Java Swing program to perform matrix addition of two 2×2 matrices and display the resultant matrix.](#Program14)

[15.  Write a Java Swing program to create a JFrame containing 10 buttons. When each button is clicked, a different shape such as circle, oval, rectangle, square, line, arc, triangle, polygon, etc. should be drawn on the frame. ](#Program15)

[16.Write a Java program using Mouse Events to create a simple paint brush application with the selection of color and brush width.](#Program16)

[17.Create a package of any five classes of your choice, import that package into another Java program, and test all the classes.](#Program17)

[18.  Create one package and sub package  import and test it .](#Program18)

[19. Create an array of size 5 in Java and demonstrate ArrayIndexOutOfBoundsException using try-catch. Also demonstrate ArithmeticException in the same program and display proper messages in the catch block.](#Program19)

[20.Write a Java program to test the valid age range of a student using a user-defined exception. If the age is not within the valid range, throw and handle the exception with a proper message.](#Program20)

[21.  File Handling Programs (given in the PPT)](#Program21)

[22.Write Java programs to demonstrate the concepts of inheritance, interface, and abstract class.](#Program22)




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

## Program11

```
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/GUIForms/JFrame.java to edit this template
 */

/**
 *
 * @author DELL
 */
public class UserFrame extends javax.swing.JFrame {
    
    private static final java.util.logging.Logger logger = java.util.logging.Logger.getLogger(UserFrame.class.getName());

    /**
     * Creates new form UserFrame
     */
    public UserFrame() {
        initComponents();
    }

    /**
     * This method is called from within the constructor to initialize the form.
     * WARNING: Do NOT modify this code. The content of this method is always
     * regenerated by the Form Editor.
     */
    @SuppressWarnings("unchecked")
    // <editor-fold defaultstate="collapsed" desc="Generated Code">                          
    private void initComponents() {

        jLabel1 = new javax.swing.JLabel();
        jLabel2 = new javax.swing.JLabel();
        jLabel3 = new javax.swing.JLabel();
        jTextField1 = new javax.swing.JTextField();
        jTextField2 = new javax.swing.JTextField();
        jTextField3 = new javax.swing.JTextField();
        jButton1 = new javax.swing.JButton();

        setDefaultCloseOperation(javax.swing.WindowConstants.EXIT_ON_CLOSE);

        jLabel1.setText("First Name");

        jLabel2.setText("Last Name");

        jLabel3.setText("Full Name");

        jTextField1.addActionListener(this::jTextField1ActionPerformed);

        jTextField2.addActionListener(this::jTextField2ActionPerformed);

        jTextField3.addActionListener(this::jTextField3ActionPerformed);

        jButton1.setText("Submit");
        jButton1.addActionListener(this::jButton1ActionPerformed);

        javax.swing.GroupLayout layout = new javax.swing.GroupLayout(getContentPane());
        getContentPane().setLayout(layout);
        layout.setHorizontalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(layout.createSequentialGroup()
                        .addGap(18, 18, 18)
                        .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                            .addGroup(javax.swing.GroupLayout.Alignment.TRAILING, layout.createSequentialGroup()
                                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                                    .addComponent(jLabel3)
                                    .addComponent(jLabel2))
                                .addGap(73, 73, 73))
                            .addGroup(layout.createSequentialGroup()
                                .addComponent(jLabel1)
                                .addGap(53, 53, 53)))
                        .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.TRAILING, false)
                            .addComponent(jTextField1, javax.swing.GroupLayout.DEFAULT_SIZE, 158, Short.MAX_VALUE)
                            .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING, false)
                                .addComponent(jTextField2, javax.swing.GroupLayout.DEFAULT_SIZE, 158, Short.MAX_VALUE)
                                .addComponent(jTextField3))))
                    .addGroup(layout.createSequentialGroup()
                        .addGap(27, 27, 27)
                        .addComponent(jButton1)))
                .addContainerGap(95, Short.MAX_VALUE))
        );
        layout.setVerticalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addContainerGap()
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(jLabel1)
                    .addComponent(jTextField1, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addGap(27, 27, 27)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(jLabel2)
                    .addComponent(jTextField2, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addGap(27, 27, 27)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(jLabel3)
                    .addComponent(jTextField3, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addGap(18, 18, 18)
                .addComponent(jButton1)
                .addContainerGap(133, Short.MAX_VALUE))
        );

        pack();
    }// </editor-fold>                        

    private void jTextField1ActionPerformed(java.awt.event.ActionEvent evt) {                                            
        // TODO add your handling code here:
    }                                           

    private void jTextField2ActionPerformed(java.awt.event.ActionEvent evt) {                                            
        // TODO add your handling code here:
    }                                           

    private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {                                         
    String firstName = jTextField1.getText();
    String lastName = jTextField2.getText();

    String fullName = firstName + " " + lastName;

    jTextField3.setText(fullName);    }                                        

    private void jTextField3ActionPerformed(java.awt.event.ActionEvent evt) {                                            
        // TODO add your handling code here:
    }                                           

    /**
     * @param args the command line arguments
     */
    public static void main(String args[]) {
        /* Set the Nimbus look and feel */
        //<editor-fold defaultstate="collapsed" desc=" Look and feel setting code (optional) ">
        /* If Nimbus (introduced in Java SE 6) is not available, stay with the default look and feel.
         * For details see http://download.oracle.com/javase/tutorial/uiswing/lookandfeel/plaf.html 
         */
        try {
            for (javax.swing.UIManager.LookAndFeelInfo info : javax.swing.UIManager.getInstalledLookAndFeels()) {
                if ("Nimbus".equals(info.getName())) {
                    javax.swing.UIManager.setLookAndFeel(info.getClassName());
                    break;
                }
            }
        } catch (ReflectiveOperationException | javax.swing.UnsupportedLookAndFeelException ex) {
            logger.log(java.util.logging.Level.SEVERE, null, ex);
        }
        //</editor-fold>

        /* Create and display the form */
        java.awt.EventQueue.invokeLater(() -> new UserFrame().setVisible(true));
    }

    // Variables declaration - do not modify                     
    private javax.swing.JButton jButton1;
    private javax.swing.JLabel jLabel1;
    private javax.swing.JLabel jLabel2;
    private javax.swing.JLabel jLabel3;
    private javax.swing.JTextField jTextField1;
    private javax.swing.JTextField jTextField2;
    private javax.swing.JTextField jTextField3;
    // End of variables declaration                   
}
```

<img width="396" height="356" alt="image" src="https://github.com/user-attachments/assets/987640ef-e193-4d51-8040-b9f88b80e88b" />

## Program13
```
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class CalculatorSwing extends JFrame implements ActionListener {

    JTextField display;
    JButton[] numberButtons = new JButton[10];
    JButton addButton, subButton, mulButton, divButton;
    JButton equalButton, clearButton, deleteButton, dotButton;

    JPanel panel;

    Font myFont = new Font("Arial", Font.BOLD, 22);

    double num1 = 0, num2 = 0, result = 0;
    char operator;

    CalculatorSwing() {
        setTitle("Calculator");
        setSize(420, 550);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLocationRelativeTo(null);
        setLayout(null);
        getContentPane().setBackground(new Color(245, 245, 245));

        display = new JTextField();
        display.setBounds(30, 30, 340, 60);
        display.setFont(new Font("Arial", Font.BOLD, 28));
        display.setEditable(false);
        display.setHorizontalAlignment(JTextField.RIGHT);
        display.setBackground(Color.WHITE);
        display.setForeground(Color.BLACK);
        display.setBorder(BorderFactory.createLineBorder(Color.GRAY, 2));
        add(display);

        addButton = new JButton("+");
        subButton = new JButton("-");
        mulButton = new JButton("*");
        divButton = new JButton("/");
        equalButton = new JButton("=");
        clearButton = new JButton("C");
        deleteButton = new JButton("Del");
        dotButton = new JButton(".");

        JButton[] functionButtons = {
            addButton, subButton, mulButton, divButton,
            equalButton, clearButton, deleteButton, dotButton
        };

        for (int i = 0; i < 10; i++) {
            numberButtons[i] = new JButton(String.valueOf(i));
            numberButtons[i].setFont(myFont);
            numberButtons[i].setFocusable(false);
            numberButtons[i].setBackground(new Color(255, 255, 255));
            numberButtons[i].addActionListener(this);
        }

        for (JButton button : functionButtons) {
            button.setFont(myFont);
            button.setFocusable(false);
            button.setBackground(new Color(220, 220, 220));
            button.addActionListener(this);
        }

        clearButton.setBackground(new Color(255, 153, 153));
        deleteButton.setBackground(new Color(255, 204, 153));
        equalButton.setBackground(new Color(153, 255, 153));
        addButton.setBackground(new Color(204, 229, 255));
        subButton.setBackground(new Color(204, 229, 255));
        mulButton.setBackground(new Color(204, 229, 255));
        divButton.setBackground(new Color(204, 229, 255));

        panel = new JPanel();
        panel.setBounds(30, 120, 340, 320);
        panel.setLayout(new GridLayout(4, 4, 10, 10));
        panel.setBackground(new Color(245, 245, 245));

        panel.add(numberButtons[1]);
        panel.add(numberButtons[2]);
        panel.add(numberButtons[3]);
        panel.add(addButton);

        panel.add(numberButtons[4]);
        panel.add(numberButtons[5]);
        panel.add(numberButtons[6]);
        panel.add(subButton);

        panel.add(numberButtons[7]);
        panel.add(numberButtons[8]);
        panel.add(numberButtons[9]);
        panel.add(mulButton);

        panel.add(dotButton);
        panel.add(numberButtons[0]);
        panel.add(equalButton);
        panel.add(divButton);

        add(panel);

        clearButton.setBounds(30, 460, 160, 40);
        deleteButton.setBounds(210, 460, 160, 40);

        add(clearButton);
        add(deleteButton);

        setVisible(true);
    }

    public void actionPerformed(ActionEvent e) {

        for (int i = 0; i < 10; i++) {
            if (e.getSource() == numberButtons[i]) {
                display.setText(display.getText().concat(String.valueOf(i)));
            }
        }

        if (e.getSource() == dotButton) {
            if (!display.getText().contains(".")) {
                display.setText(display.getText().concat("."));
            }
        }

        if (e.getSource() == addButton) {
            if (!display.getText().isEmpty()) {
                num1 = Double.parseDouble(display.getText());
                operator = '+';
                display.setText("");
            }
        }

        if (e.getSource() == subButton) {
            if (!display.getText().isEmpty()) {
                num1 = Double.parseDouble(display.getText());
                operator = '-';
                display.setText("");
            }
        }

        if (e.getSource() == mulButton) {
            if (!display.getText().isEmpty()) {
                num1 = Double.parseDouble(display.getText());
                operator = '*';
                display.setText("");
            }
        }

        if (e.getSource() == divButton) {
            if (!display.getText().isEmpty()) {
                num1 = Double.parseDouble(display.getText());
                operator = '/';
                display.setText("");
            }
        }

        if (e.getSource() == equalButton) {
            if (!display.getText().isEmpty()) {
                num2 = Double.parseDouble(display.getText());

                switch (operator) {
                    case '+':
                        result = num1 + num2;
                        break;
                    case '-':
                        result = num1 - num2;
                        break;
                    case '*':
                        result = num1 * num2;
                        break;
                    case '/':
                        if (num2 == 0) {
                            JOptionPane.showMessageDialog(this, "Cannot divide by zero");
                            display.setText("");
                            return;
                        }
                        result = num1 / num2;
                        break;
                }

                if (result == (int) result) {
                    display.setText(String.valueOf((int) result));
                } else {
                    display.setText(String.valueOf(result));
                }

                num1 = result;
            }
        }

        if (e.getSource() == clearButton) {
            display.setText("");
            num1 = 0;
            num2 = 0;
            result = 0;
        }

        if (e.getSource() == deleteButton) {
            String text = display.getText();
            if (!text.isEmpty()) {
                display.setText(text.substring(0, text.length() - 1));
            }
        }
    }

    public static void main(String[] args) {
        new CalculatorSwing();
    }
}
```

<img width="390" height="538" alt="image" src="https://github.com/user-attachments/assets/cec31415-1696-46c1-84fd-1d985cf4949b" />


## Program14

```
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class MatrixAdditionSwing extends JFrame implements ActionListener {

    JTextField[][] matrixA = new JTextField[3][3];
    JTextField[][] matrixB = new JTextField[3][3];
    JTextField[][] resultMatrix = new JTextField[3][3];

    JButton addButton, clearButton;
    JLabel titleLabel, labelA, labelB, labelResult;

    Font titleFont = new Font("Arial", Font.BOLD, 24);
    Font labelFont = new Font("Arial", Font.BOLD, 18);
    Font fieldFont = new Font("Arial", Font.PLAIN, 18);

    MatrixAdditionSwing() {
        setTitle("Matrix Addition Using Swing");
        setSize(850, 600);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLocationRelativeTo(null);
        setLayout(null);
        getContentPane().setBackground(new Color(245, 248, 255));

        titleLabel = new JLabel("Matrix Addition Calculator");
        titleLabel.setFont(titleFont);
        titleLabel.setBounds(260, 20, 350, 40);
        titleLabel.setForeground(new Color(30, 60, 120));
        add(titleLabel);

        labelA = new JLabel("Matrix A");
        labelA.setFont(labelFont);
        labelA.setBounds(120, 80, 120, 30);
        add(labelA);

        labelB = new JLabel("Matrix B");
        labelB.setFont(labelFont);
        labelB.setBounds(360, 80, 120, 30);
        add(labelB);

        labelResult = new JLabel("Result Matrix");
        labelResult.setFont(labelFont);
        labelResult.setBounds(600, 80, 150, 30);
        add(labelResult);

        createMatrix(matrixA, 70, 130);
        createMatrix(matrixB, 320, 130);
        createResultMatrix(resultMatrix, 570, 130);

        addButton = new JButton("Add Matrices");
        addButton.setBounds(250, 420, 150, 45);
        addButton.setFont(new Font("Arial", Font.BOLD, 16));
        addButton.setBackground(new Color(153, 255, 153));
        addButton.addActionListener(this);
        add(addButton);

        clearButton = new JButton("Clear");
        clearButton.setBounds(430, 420, 150, 45);
        clearButton.setFont(new Font("Arial", Font.BOLD, 16));
        clearButton.setBackground(new Color(255, 204, 153));
        clearButton.addActionListener(this);
        add(clearButton);

        JLabel note = new JLabel("Enter integer values in both matrices and click Add Matrices.");
        note.setFont(new Font("Arial", Font.ITALIC, 15));
        note.setBounds(180, 490, 500, 30);
        note.setForeground(Color.DARK_GRAY);
        add(note);

        setVisible(true);
    }

    void createMatrix(JTextField[][] matrix, int startX, int startY) {
        int width = 50;
        int height = 40;
        int gap = 10;

        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                matrix[i][j] = new JTextField();
                matrix[i][j].setBounds(startX + j * (width + gap), startY + i * (height + gap), width, height);
                matrix[i][j].setFont(fieldFont);
                matrix[i][j].setHorizontalAlignment(JTextField.CENTER);
                matrix[i][j].setBackground(Color.WHITE);
                matrix[i][j].setBorder(BorderFactory.createLineBorder(new Color(100, 100, 100), 2));
                add(matrix[i][j]);
            }
        }
    }

    void createResultMatrix(JTextField[][] matrix, int startX, int startY) {
        int width = 50;
        int height = 40;
        int gap = 10;

        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                matrix[i][j] = new JTextField();
                matrix[i][j].setBounds(startX + j * (width + gap), startY + i * (height + gap), width, height);
                matrix[i][j].setFont(fieldFont);
                matrix[i][j].setHorizontalAlignment(JTextField.CENTER);
                matrix[i][j].setEditable(false);
                matrix[i][j].setBackground(new Color(230, 255, 230));
                matrix[i][j].setBorder(BorderFactory.createLineBorder(new Color(0, 128, 0), 2));
                add(matrix[i][j]);
            }
        }
    }

    public void actionPerformed(ActionEvent e) {
        if (e.getSource() == addButton) {
            try {
                for (int i = 0; i < 3; i++) {
                    for (int j = 0; j < 3; j++) {
                        int a = Integer.parseInt(matrixA[i][j].getText());
                        int b = Integer.parseInt(matrixB[i][j].getText());
                        int sum = a + b;
                        resultMatrix[i][j].setText(String.valueOf(sum));
                    }
                }
            } catch (NumberFormatException ex) {
                JOptionPane.showMessageDialog(this, "Please enter valid integer values in all boxes.");
            }
        }

        if (e.getSource() == clearButton) {
            for (int i = 0; i < 3; i++) {
                for (int j = 0; j < 3; j++) {
                    matrixA[i][j].setText("");
                    matrixB[i][j].setText("");
                    resultMatrix[i][j].setText("");
                }
            }
        }
    }

    public static void main(String[] args) {
        new MatrixAdditionSwing();
    }
}
```
<img width="833" height="587" alt="image" src="https://github.com/user-attachments/assets/7ecfe637-9222-47e7-96c5-1f574b7e7ec0" />

## Program15

```
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class ShapeButtonsFrame extends JFrame implements ActionListener {

    JButton circleBtn, ovalBtn, rectBtn, squareBtn, lineBtn;
    JButton arcBtn, triangleBtn, diamondBtn, polygonBtn, fillOvalBtn;

    DrawingPanel drawingPanel;
    String currentShape = "";

    Font btnFont = new Font("Arial", Font.BOLD, 14);

    ShapeButtonsFrame() {
        setTitle("Shape Drawing Using 10 Buttons");
        setSize(900, 600);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLocationRelativeTo(null);
        setLayout(new BorderLayout());

        JPanel topPanel = new JPanel();
        topPanel.setLayout(new GridLayout(2, 5, 10, 10));
        topPanel.setBackground(new Color(240, 248, 255));
        topPanel.setBorder(BorderFactory.createEmptyBorder(15, 15, 15, 15));

        circleBtn = createButton("Circle", new Color(255, 204, 204));
        ovalBtn = createButton("Oval", new Color(255, 229, 204));
        rectBtn = createButton("Rectangle", new Color(255, 255, 204));
        squareBtn = createButton("Square", new Color(204, 255, 204));
        lineBtn = createButton("Line", new Color(204, 255, 255));
        arcBtn = createButton("Arc", new Color(204, 229, 255));
        triangleBtn = createButton("Triangle", new Color(229, 204, 255));
        diamondBtn = createButton("Diamond", new Color(255, 204, 229));
        polygonBtn = createButton("Polygon", new Color(220, 220, 220));
        fillOvalBtn = createButton("Fill Oval", new Color(255, 180, 180));

        topPanel.add(circleBtn);
        topPanel.add(ovalBtn);
        topPanel.add(rectBtn);
        topPanel.add(squareBtn);
        topPanel.add(lineBtn);
        topPanel.add(arcBtn);
        topPanel.add(triangleBtn);
        topPanel.add(diamondBtn);
        topPanel.add(polygonBtn);
        topPanel.add(fillOvalBtn);

        drawingPanel = new DrawingPanel();
        drawingPanel.setBackground(Color.WHITE);

        JLabel heading = new JLabel("Click any button to draw a shape", JLabel.CENTER);
        heading.setFont(new Font("Arial", Font.BOLD, 24));
        heading.setForeground(new Color(40, 40, 120));
        heading.setBorder(BorderFactory.createEmptyBorder(10, 10, 10, 10));

        add(heading, BorderLayout.NORTH);
        add(topPanel, BorderLayout.SOUTH);
        add(drawingPanel, BorderLayout.CENTER);

        setVisible(true);
    }

    JButton createButton(String text, Color color) {
        JButton btn = new JButton(text);
        btn.setFont(btnFont);
        btn.setBackground(color);
        btn.setFocusable(false);
        btn.addActionListener(this);
        return btn;
    }

    public void actionPerformed(ActionEvent e) {
        currentShape = e.getActionCommand();
        drawingPanel.repaint();
    }

    class DrawingPanel extends JPanel {
        protected void paintComponent(Graphics g) {
            super.paintComponent(g);

            Graphics2D g2 = (Graphics2D) g;
            g2.setStroke(new BasicStroke(3));
            g2.setColor(new Color(50, 50, 50));

            if (currentShape.equals("Circle")) {
                g2.drawOval(320, 120, 150, 150);
            }
            else if (currentShape.equals("Oval")) {
                g2.drawOval(280, 140, 220, 120);
            }
            else if (currentShape.equals("Rectangle")) {
                g2.drawRect(280, 140, 220, 120);
            }
            else if (currentShape.equals("Square")) {
                g2.drawRect(320, 120, 150, 150);
            }
            else if (currentShape.equals("Line")) {
                g2.drawLine(250, 100, 550, 250);
            }
            else if (currentShape.equals("Arc")) {
                g2.drawArc(280, 120, 220, 150, 0, 180);
            }
            else if (currentShape.equals("Triangle")) {
                int[] x = {390, 300, 480};
                int[] y = {100, 250, 250};
                g2.drawPolygon(x, y, 3);
            }
            else if (currentShape.equals("Diamond")) {
                int[] x = {390, 320, 390, 460};
                int[] y = {100, 180, 260, 180};
                g2.drawPolygon(x, y, 4);
            }
            else if (currentShape.equals("Polygon")) {
                int[] x = {330, 380, 450, 430, 350, 300};
                int[] y = {120, 90, 130, 210, 240, 180};
                g2.drawPolygon(x, y, 6);
            }
            else if (currentShape.equals("Fill Oval")) {
                g2.setColor(new Color(255, 120, 120));
                g2.fillOval(300, 130, 200, 120);
            }
        }
    }

    public static void main(String[] args) {
        new ShapeButtonsFrame();
    }
}
```
<img width="887" height="591" alt="image" src="https://github.com/user-attachments/assets/fdf11559-055b-4b04-a2ab-2ee3b77dff9a" />

## Program16
```
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
import java.util.ArrayList;

public class PaintBrushApp extends JFrame {

    JComboBox<String> colorBox;
    JComboBox<Integer> sizeBox;
    JButton clearButton;

    DrawPanel drawPanel;

    Color selectedColor = Color.BLACK;
    int brushSize = 5;

    ArrayList<BrushPoint> points = new ArrayList<>();

    PaintBrushApp() {
        setTitle("Paint Brush Using Mouse Events");
        setSize(900, 600);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLocationRelativeTo(null);
        setLayout(new BorderLayout());

        JPanel topPanel = new JPanel();
        topPanel.setBackground(new Color(230, 240, 255));
        topPanel.setLayout(new FlowLayout(FlowLayout.LEFT, 20, 10));

        JLabel titleLabel = new JLabel("Simple Paint Brush");
        titleLabel.setFont(new Font("Arial", Font.BOLD, 22));
        titleLabel.setForeground(new Color(30, 60, 120));

        JLabel colorLabel = new JLabel("Select Color:");
        colorLabel.setFont(new Font("Arial", Font.BOLD, 16));

        String[] colors = {"Black", "Red", "Blue", "Green", "Pink", "Orange"};
        colorBox = new JComboBox<>(colors);
        colorBox.setFont(new Font("Arial", Font.PLAIN, 15));

        JLabel sizeLabel = new JLabel("Brush Width:");
        sizeLabel.setFont(new Font("Arial", Font.BOLD, 16));

        Integer[] sizes = {2, 4, 6, 8, 10, 12, 15, 20};
        sizeBox = new JComboBox<>(sizes);
        sizeBox.setFont(new Font("Arial", Font.PLAIN, 15));

        clearButton = new JButton("Clear");
        clearButton.setFont(new Font("Arial", Font.BOLD, 15));
        clearButton.setBackground(new Color(255, 180, 180));

        topPanel.add(titleLabel);
        topPanel.add(colorLabel);
        topPanel.add(colorBox);
        topPanel.add(sizeLabel);
        topPanel.add(sizeBox);
        topPanel.add(clearButton);

        drawPanel = new DrawPanel();
        drawPanel.setBackground(Color.WHITE);

        add(topPanel, BorderLayout.NORTH);
        add(drawPanel, BorderLayout.CENTER);

        colorBox.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                String colorName = (String) colorBox.getSelectedItem();

                if (colorName.equals("Black")) {
                    selectedColor = Color.BLACK;
                } else if (colorName.equals("Red")) {
                    selectedColor = Color.RED;
                } else if (colorName.equals("Blue")) {
                    selectedColor = Color.BLUE;
                } else if (colorName.equals("Green")) {
                    selectedColor = Color.GREEN;
                } else if (colorName.equals("Pink")) {
                    selectedColor = Color.PINK;
                } else if (colorName.equals("Orange")) {
                    selectedColor = Color.ORANGE;
                }
            }
        });

        sizeBox.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                brushSize = (Integer) sizeBox.getSelectedItem();
            }
        });

        clearButton.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                points.clear();
                drawPanel.repaint();
            }
        });

        setVisible(true);
    }

    class BrushPoint {
        int x, y, size;
        Color color;

        BrushPoint(int x, int y, Color color, int size) {
            this.x = x;
            this.y = y;
            this.color = color;
            this.size = size;
        }
    }

    class DrawPanel extends JPanel implements MouseMotionListener, MouseListener {

        DrawPanel() {
            addMouseMotionListener(this);
            addMouseListener(this);
        }

        public void mouseDragged(MouseEvent e) {
            points.add(new BrushPoint(e.getX(), e.getY(), selectedColor, brushSize));
            repaint();
        }

        public void paintComponent(Graphics g) {
            super.paintComponent(g);

            for (BrushPoint p : points) {
                g.setColor(p.color);
                g.fillOval(p.x, p.y, p.size, p.size);
            }
        }

        public void mouseMoved(MouseEvent e) { }
        public void mouseClicked(MouseEvent e) { }
        public void mousePressed(MouseEvent e) { }
        public void mouseReleased(MouseEvent e) { }
        public void mouseEntered(MouseEvent e) { }
        public void mouseExited(MouseEvent e) { }
    }

    public static void main(String[] args) {
        new PaintBrushApp();
    }
}
```
<img width="874" height="594" alt="image" src="https://github.com/user-attachments/assets/36a6851e-def3-46bb-8191-eee806083bf5" />

## Program19
```

public class ExceptionDemo {
    public static void main(String[] args) {

        // ArrayIndexOutOfBoundsException demonstration
        try {
            int[] arr = new int[5];

            arr[0] = 10;
            arr[1] = 20;
            arr[2] = 30;
            arr[3] = 40;
            arr[4] = 50;

            System.out.println("Trying to access 6th element...");
            System.out.println(arr[5]);   // invalid index
        }
        catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("ArrayIndexOutOfBoundsException caught!");
            System.out.println("Message: Array index is out of range.");
        }

        System.out.println();

        // ArithmeticException demonstration
        try {
            int a = 10;
            int b = 0;
            int c = a / b;

            System.out.println("Result = " + c);
        }
        catch (ArithmeticException e) {
            System.out.println("ArithmeticException caught!");
            System.out.println("Message: Division by zero is not allowed.");
        }

        System.out.println();
        System.out.println("Program ended successfully after handling exceptions.");
    }
}
```
<img width="346" height="124" alt="image" src="https://github.com/user-attachments/assets/ccc14064-77d6-4047-9830-b41aae20929e" />

## Program20
```
import java.util.Scanner;
class InvalidAgeException extends Exception {

    public InvalidAgeException(String message) {
        super(message);
    }
}

public class StudentAgeTest {

    // method to check age
    static void checkAge(int age) throws InvalidAgeException {
        if (age < 5 || age > 25) {
            throw new InvalidAgeException("Invalid Age! Age must be between 5 and 25.");
        } else {
            System.out.println("Valid student age.");
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        try {
            System.out.print("Enter student age: ");
            int age = sc.nextInt();

            checkAge(age);   // calling method

        } catch (InvalidAgeException e) {
            System.out.println("User Defined Exception Caught!");
            System.out.println("Message: " + e.getMessage());
        } catch (Exception e) {
            System.out.println("Please enter a valid number.");
        }

        sc.close();
    }
}
```
<img width="371" height="64" alt="image" src="https://github.com/user-attachments/assets/17581033-4b50-41f5-b187-1cc869c037f7" />

## Program22

```
// -------- INTERFACE --------
interface Printable {
    void print();
}

// -------- ABSTRACT CLASS --------
abstract class Shape {
    abstract void draw();

    void message() {
        System.out.println("This is an abstract class.");
    }
}

// -------- INHERITANCE --------
class Animal {
    void eat() {
        System.out.println("Animal eats food.");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks.");
    }
}

// -------- CLASS IMPLEMENTING INTERFACE --------
class Document implements Printable {
    public void print() {
        System.out.println("Printing document using interface.");
    }
}

// -------- CLASS EXTENDING ABSTRACT CLASS --------
class Circle extends Shape {
    void draw() {
        System.out.println("Drawing a circle.");
    }
}

// -------- MAIN CLASS --------
public class ConceptDemo {
    public static void main(String[] args) {

        // Inheritance
        System.out.println("---- INHERITANCE ----");
        Dog d = new Dog();
        d.eat();
        d.bark();

        System.out.println();

        // Interface
        System.out.println("---- INTERFACE ----");
        Document doc = new Document();
        doc.print();

        System.out.println();

        // Abstract Class
        System.out.println("---- ABSTRACT CLASS ----");
        Circle c = new Circle();
        c.draw();
        c.message();
    }
}
```
<img width="321" height="149" alt="image" src="https://github.com/user-attachments/assets/a3b289f5-4ffa-47f6-aa55-dddfde283e9c" />











