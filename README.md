public class FactorionChecker {
    public static int factorial(int n) {
        int fact = 1;
        for (int i = 2; i <= n; i++) {
            fact *= i;
        }
        return fact;
    }

    public static boolean isFactorion(int number) {
        int original = number;
        int sum = 0;
        while (number > 0) {
            int digit = number % 10;
            sum += factorial(digit);
            number /= 10;
        }
        return sum == original;
    }
}




import java.util.Scanner;
public class MainClass {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter the lower bound of the range: ");
        int lower = sc.nextInt();
        System.out.print("Enter the upper bound of the range: ");
        int upper = sc.nextInt();
        System.out.println("Factorion numbers in the range:");
        boolean found = false;
        for (int i = lower; i <= upper; i++) {
            if (FactorionChecker.isFactorion(i)) {
                System.out.println(i);
                found = true;
            }
        }
        if (!found) {
            System.out.println("No factorion numbers found in the given range.");
        }
        sc.close();
    }
}
