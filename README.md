import java.util.Scanner;

// Class 1: Factorial calculation
class FactorialCalculator {

    int factorial(int n) {
        int fact = 1;
        for (int i = 1; i <= n; i++) {
            fact *= i;
        }
        return fact;
    }
}

// Class 2: Factorion finder (Main class)
public class Factorion {

    boolean isFactorion(int number) {

        FactorialCalculator fc = new FactorialCalculator();
        int temp = number;
        int sum = 0;

        while (temp > 0) {
            int digit = temp % 10;
            sum += fc.factorial(digit);
            temp /= 10;
        }

        return sum == number;
    }

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        Factorion obj = new Factorion();

        System.out.print("Enter the range limit: ");
        int limit = sc.nextInt();

        int count = 0;

        System.out.println("\nFactorion numbers are:");
        for (int i = 1; i <= limit; i++) {
            if (obj.isFactorion(i)) {
                System.out.println(i);
                count++;
            }
        }

        System.out.println("\nTotal Factorion Numbers = " + count);
        sc.close();
    }
}
