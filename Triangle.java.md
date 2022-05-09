`//Шарапов В.Н. ИВТ-20

package com.company;

public class Triangle {          // класс треугольник
    private double a;               // сторона а
    
    private double b;               // сторона b
    
    private double c;               // сторона c
    

    public Triangle() {          // Констр. По умолчанию
        set_a(0);
        set_b(0);
        set_c(0);
    }

    public Triangle(Triangle t) {           // перегрузка конст. с параметрами
        set_all(t);
    }

    public Triangle(double A, double B, double C) {   // констр. с параметрами
        set_all(A,B,C);
    }

    /* Вводим данные: */
    public void set_a(double A) {                  // Сторона а
        if (A < 0){
            throw new ArithmeticException("Side cannot be negative!");
        } else a = A;
    }

    public void set_b(double B) {                  // Сторона b
        if (B < 0) {
            throw new ArithmeticException("Side cannot be negative!");
        } else b = B;
    }

    public void set_c(double C) {                  // Сторона с
        if (C < 0) {
            throw new ArithmeticException("Side cannot be negative!");
        } else c = C;
    }

    public void set_all(double A, double B, double C) {         // Вводим стороны
        if (check(A, B, C))
        {
            throw new ArithmeticException("The triangle doesn't exist. ");
        }
        else
        {
            set_a(A);
            set_b(B);
            set_c(C);
        }
    }

    public void set_all(Triangle t) {                           // перегрузка установления всего
        set_a(t.a);
        set_b(t.b);
        set_c(t.c);
    }

    /* Получение данных: */

    public double get_a()
    {
        return a;
    }

    public double get_b()
    {
        return b;
    }

    public double get_c()
    {
        return c;
    }

    public static boolean check(double A, double B, double C){             //Функц. проверки
        if ((A + B > C) && (B + C > A) && (A + C > B))
        {
            return false;
        }
        else
        {
            //System.out.println("The triangle doesn't exist.");
            return true;
        }
    }

    public double search_S()											//Функция поиска площади
    {
        double p, S;


        p = (a + b + c) / 2;
        S = Math.sqrt(p * (p - a) * (p - b) * (p - c));

        return S;
    }

    public double search_P()												//Функция поиска периметра
    {
        double P;

        P = a + b + c;

        return P;
    }

    public double search_A()												//Функция поиска угла А
    {
        double cos_A, A = 0;

        cos_A = (a * a + c * c - b * b) / (2 * a * c);

        A = Math.acos(cos_A);

        return A;

    }

    public double search_B()												//Функция поиска угла B
    {
        double cos_B, B = 0;

        cos_B = (a * a + b * b - c * c) / (2 * a * b);

        B = Math.acos(cos_B);

        return B;

    }

    public double search_C()												//Функция поиска угла С
    {
        double cos_C, C = 0;

        cos_C = (b * b + c * c - a * a) / (2 * c * b);

        C = Math.acos(cos_C);

        return C;
    }


}
`
