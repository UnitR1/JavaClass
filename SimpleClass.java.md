`package com.company;

public class SimpleClass {
    public static void main(String[] args){

        Triangle t1 = new Triangle();                                       // создание класса

        System.out.println("Enter the sides of the triangle a, b, c");

        try {                                                               // Проверка на правильность треугольника
            t1.set_all(3, 5, 7);
        } catch (ArithmeticException e) {
            System.out.println(e);
        }
        System.out.println("Injection A: " + t1.search_A());                // Поиск угла А
        System.out.println("Injection B: " + t1.search_B());                // Поиск угла В
        System.out.println("Injection C: " + t1.search_C());                // Поиск угла С
        double a = Math.round(t1.search_S()*1000);                          // Поиск площади
        System.out.println("S = " + (a/1000));
        //System.out.println("S = " + t1.search_S());

        System.out.println("P = " + Math.round(t1.search_P()*1000)/1000);   // Поиск периметра

        Triangle t2 = new Triangle();                                       // Создание класса t2

        System.out.println("Enter the sides of the triangle a, b, c");

        try {                                                               // Класс создавался для проверки >>
            t2.set_all(1, 2, 3);                                   // >> правильности работы ввода правильного треугольника
        } catch (ArithmeticException e) {
            System.out.println(e);
        }

        System.out.println();

    }`
