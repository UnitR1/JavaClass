`
import com.company.Triangle;

import javax.swing.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import static java.lang.Math.toDegrees;
import static javax.swing.JOptionPane.showMessageDialog;

public class MainFrame extends JFrame {
    private JTextField SideA;                       // Текстовое поле А
    private JTextField SideB;                       // Текстовое поле B
    private JTextField SideC;                       // Текстовое поле C
    private JTextField SquareS;                     // Текстовое поле S
    private JTextField PerP;                        // Текстовое поле P
    private JTextField InjA;                        // Текстовое поле угол А
    private JTextField InjB;                        // Текстовое поле угол B
    private JTextField InjC;                        // Текстовое поле угол C
    private JButton Calcul;                         // Кнопка "Вычислить"
    private JButton DelBut;                         // Кнопка "Очистить"
    private JPanel mainPanel;                       // Главное окно

    private void SetDefaultCloseOperation(int exitOnClose) {
    }

    public static void main(String[] args) {                                        // Создание интерфейса
        MainFrame myFrame = new MainFrame();
    }

    public MainFrame() {
        setContentPane(mainPanel);                                             // Для получение GUI
        setTitle("Welcome");                                                   // Название Окна
        setSize(450,300);                                         //  Размеры окна
        SetDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);               // Закрытие окна
        setVisible(true);

        Triangle t2 = new Triangle();                                          //Создание класса

        Calcul.addActionListener(new ActionListener() {                         //Кнопка "Вычислить"
            @Override
            public void actionPerformed(ActionEvent e) {
                double A = Double.parseDouble(SideA.getText());                 // Получение стороны А
                double B = Double.parseDouble(SideB.getText());                 // Получение стороны В
                double C = Double.parseDouble(SideC.getText());                 // Получение стороны С

                try {                                                           //Проверка на правильность ввода треугольника
                    t2.set_all(A, B, C);
                } catch (ArithmeticException e1) {
                    //System.out.println(e1);
                    showMessageDialog(mainPanel, "Треугольник не правильный!");              //Вывод отдельного окна в случае ввода неправельных значений
                }

                SquareS.setText(Double.toString(t2.search_S()));                    // Вычисление площади
                PerP.setText(Double.toString(t2.search_P()));                       // Вычисление периметра
                InjA.setText(Double.toString(toDegrees(t2.search_A())));            // Вычисление угла А
                InjB.setText(Double.toString(toDegrees(t2.search_B())));            // Вычисление угла В
                InjC.setText(Double.toString(toDegrees(t2.search_C())));            // Вычисление угла С


            }
        });
        DelBut.addActionListener(new ActionListener() {                             // Кнопка "Отчистить"
            @Override
            public void actionPerformed(ActionEvent e) {
                SideA.setText("");                                                  // Просто делаем пустые поля
                SideB.setText("");
                SideC.setText("");
                SquareS.setText("");
                PerP.setText("");
                InjA.setText("");
                InjB.setText("");
                InjC.setText("");
            }
        });
    }



}

`


![image](https://user-images.githubusercontent.com/97575881/167413954-dc1695f6-564f-4008-8d23-694b63ff798c.png)
