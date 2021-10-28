# java_odevlerim
#### 1-)Math işlevlerini kullanarak parçalı işlevi hesaplayan bir program yazın
```java
import java.util.Scanner;
import java.lang.Math;

public class Main
{
    public static void main(String[] args) {
        double y;
        double two_thirds = 2.0 / 3.0;
        
        Scanner sc = new Scanner(System.in);
        System.out.print("Lütfen bir adet x değeri giriniz: ");
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
#### 2-)Bir ondalık sayı (x) giren ve aşağıdaki formüle göre sonucu (y) bularak çıktıda veren programı yazınız.
```java
import java.util.Scanner;
import java.lang.Math;

public class Main
{
    public static void main(String[] args) {
        double y;
        
        Scanner sc = new Scanner(System.in);
        System.out.print("1 adet x sayısı giriniz: ");
        double x = sc.nextDouble();
        sc.close();

        y = x - Math.pow(x, 3)/6 + Math.pow(x, 5)/120 - Math.pow(x, 7)/5040;

        System.out.println("Fonksiyon Sonucu: " + y);
    }
} 
```
#### 3-)x'in sıfırdan büyük veya sıfıra küçük eşit olma durumuna göre belirli f(x) ve g(x) fonksiyonlarının ekrana çıktılarını veren programı yazınız.
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
#### 4-)Girilen x değerlerine göre fx değerini hesaplayan programı yazınız.
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

        if (x < 10) 
        {
            fx = Math.abs(x);
        } 
        else if (x >= 10.0 && x < 100.0) 
        {
            fx = 3.0 / (2.0 * Math.pow(x, 2));
        } 
        else 
        {
            fx = Math.pow(x-10, 2) / Math.pow(x, 3);
        }

        System.out.printf("f(%.2f) = %.10f", x, fx);
    }
}

```
#### 5-)Bir bankada yapılan harcamaya göre kazanılan ekstra puanı hesaplayan bir program yazılacaktır.Program ilk olarak kullanıcıdan toplam harcama miktarını alacaktır.Bu miktara göre kazanılan puan aşağıdaki gibi hesaplanacaktır:
```
--->Toplam harcama 250den küçük ise her 50 TL başına 10p
--->Toplam harcama 250 ve 500 arasında ise her 50 TL başına 15p
--->Toplam harcama 500den büyük ise her 50 TL başına 20p
```
Kazanılan puan kullanıcıya iletildikten sonra bu miktarı TEMA vakfına bağış yapabileceği hakkında bilgi iletilecek.Gelen cevaba göre puan miktarı bağışlanacaktır.
```java
import java.util.*;
public class Main 
{
    public static void main(String[] args) throws Exception 
    {   
        int top_harcama, puan;
        String karar;

        Scanner klavye = new Scanner(System.in);
        System.out.print("Lütfen bankamızda şu zamana kadar yapmış olduğunuz toplam harcamayı giriniz:");
        top_harcama = klavye.nextInt();

        if (top_harcama < 250) 
        {
            puan = (top_harcama/50)*10;
        }
        else if (top_harcama > 250 && top_harcama<500 ) 
        {
            puan = (top_harcama/50)*15;
        }
        else
        {
            puan = (top_harcama/50)*20;
        }
       
        System.out.println("Kazandığınız miktar:" + puan + "TL'dir.Bu miktar ile TEMA vakfına bağışta bulunmak ister misiniz?");
        System.out.println("(y/n)");

        karar = klavye.next();

        if (karar.equals("y")) 
        {
            System.out.println("Bağışınız başarıyla gerçekleşmiştir.Teşekkürler.İyi günler dileriz.");    
        }
        else
        {
            System.exit(0);
        }
        klavye.close(); 


    }
}
```

