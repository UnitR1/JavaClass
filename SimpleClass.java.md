`package com.company;

public class SimpleClass {
    public static void main(String[] args){

        Triangle t1 = new Triangle();

        System.out.println("Enter the sides of the triangle a, b, c");

        try {
            t1.set_all(3, 5, 7);
        } catch (ArithmeticException e) {
            System.out.println(e);
        }
        System.out.println("Injection A: " + t1.search_A());
        System.out.println("Injection B: " + t1.search_B());
        System.out.println("Injection C: " + t1.search_C());
        //double a = Math.round(t1.search_S()*1000);
        //System.out.println("S = " + (a/1000));
        //System.out.println("S = " + t1.search_S());

        System.out.println("P = " + Math.round(t1.search_P()*1000)/1000);

        Triangle t2 = new Triangle();

        System.out.println("Enter the sides of the triangle a, b, c");

        try {
            t2.set_all(1, 2, 3);
        } catch (ArithmeticException e) {
            System.out.println(e);
        }

        System.out.println();

    }





}
`
