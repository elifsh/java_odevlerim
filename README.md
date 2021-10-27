# Java Ödevlerim
## 1.1 `Math` işlevlerini kullanarak parçalı işlevi hesaplayan program

```java
import java.util.Scanner;
import java.lang.Math;

public class Main
{
	public static void main(String[] args) {
		double y;
		double two_thirds = 2.0 / 3.0;

        System.out.print(">>> ");
        Scanner sc = new Scanner(System.in);
        double x = sc.nextDouble();
        sc.close();
        
        if (x < 0) {
            y = two_thirds * Math.abs(x-1);   
        } else if (x > 0) {
            y = two_thirds * Math.abs(x+1);
        } else {
            y = Math.sqrt(two_thirds);
        }
        
        System.out.println("Fonksiyon Sonucu: " + y);
	}
}
```

## 1.2 Bir ondalık sayı (x) alan ve aşağıdaki formüle göre sonucu (y) veren program

```java
import java.util.Scanner;
import java.lang.Math;

public class Main
{
    public static void main(String[] args) {
        double y;
        
        System.out.print("1 adet x sayısı giriniz: ");
        Scanner sc = new Scanner(System.in);
        double x = sc.nextDouble();
        sc.close();
        
        y = x - Math.pow(x, 3)/6 + Math.pow(x, 5)/120 - Math.pow(x, 7)/5040;
        
        System.out.println("Fonksiyon Sonucu: " + y);
    }
}
```

## 1.3 x'in sıfırdan büyük ve sıfırdan küçük veya eşit olma durumuna göre belirli f(x) ve g(x) fonksiyonlarının çıktılarını veren program

```java
import java.util.Scanner;
import java.lang.Math;

public class Main
{
    public static void main(String[] args) {   
        double fx, gx;
        
        Scanner sc = new Scanner(System.in);
        System.out.print("Lütfen bir adet sayı giriniz: ");
        double x = sc.nextInt();
        sc.close();

        double f = 1.0 / (1.0 + Math.pow(x, 2));

        if (x > 0) {
            fx = 1.0 / (1.0 + x);
            gx = f;
        } else {
            fx = f;
            gx = 1.0 / (f + x + Math.pow(x, 3));
        }
        
        System.out.printf("f(%.2f) = %f\n", x, fx);
        System.out.printf("g(%.2f) = %f\n", x, gx);
    }
}
```

## 1.4 Girilen x değerine göre f(x) değerini hesaplayan program

```java
import java.util.Scanner;
import java.lang.Math;

public class Main
{
    public static void main(String[] args) throws Exception {   
        double fx;
        
        Scanner sc = new Scanner(System.in);
        System.out.print("Lütfen bir sayı giriniz: ");
        double x = sc.nextDouble();
        sc.close();

        if (x < 10) {
            fx = Math.abs(x);
        } else if (x >= 10.0 && x < 100.0) {
            fx = 3.0 / (2.0 * Math.pow(x, 2));
        } else {
            fx = Math.pow(x-10, 2) / Math.pow(x, 3); 
        }
        
        System.out.printf("f(%.2f) = %.10f", x, fx);
    }
}
```
