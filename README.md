# Java-Secant-Method-Code

import java.util.Scanner;

public class JavaSecant {
    public static void main(String[] args) {
        Scanner reader = new Scanner(System.in);
        double xn1; //x_(n - 1)
        double xn; //x_n
        double x;
        double precision;
        System.out.print("Enter begining of interval: ");
        xn1 = reader.nextDouble();
        System.out.print("Enter end of interval: ");
        xn = reader.nextDouble();
        System.out.print("Enter precision of method: ");
        precision = reader.nextDouble();
        if (function(xn1) * function(xn) > 0.0d) {
            System.out.println("Function has same signs at ends of interval");
            return;
        }
        x = xn1;
        while(Math.abs(function(x)) > precision){
            System.out.println("X: " + x + " f(x): " + function(x));
            x = xn - ((function(xn) * (xn - xn1)) / (function(xn) - function(xn1)));
            xn1 = xn;
            xn = x;
        }
    }
    private static double function(double x) { //x^2 + 2x -1
        return (x * x * x) - (2 * x) - 5;
    }
}
