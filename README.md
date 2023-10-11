import java.util.Scanner;

public class SeriesSum {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Введите значение x: ");
        double x = scanner.nextDouble();
        
        System.out.print("Введите количество слагаемых n: ");
        int n = scanner.nextInt();
        
        System.out.print("Введите значение e: ");
        double e = scanner.nextDouble();
        
        double ln2 = Math.log(2);
        double sum = 0;
        double an = 0;
        
        for (int i = 0; i < n; i++) {
            if (i == 0) {
                an = 1;
            } else {
                an *= ln2 * x / i;
            }
            
            sum += an;
            
            if (Math.abs(an) > e) {
                System.out.println("Слагаемое " + (i + 1) + " больше e: " + an);
            }
            
            if (Math.abs(an) > e / 10) {
                System.out.println("Слагаемое " + (i + 1) + " больше e/10: " + an);
            }
        }
        
        System.out.println("Сумма " + n + " слагаемых: " + sum);
        
        double mathValue = Math.pow(2, x);
        System.out.println("Значение функции с помощью Math: " + mathValue);
    }
}
