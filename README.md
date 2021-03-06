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

        System.out.print("Bir adet sayı giriniz: ");
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
    public static void main(String[] args) {
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

## 1.5 Bir bankada yapılan harcamaya göre kazanılan ekstra puanı hesaplayan program

Program ilk olarak kullanıcıdan toplam harcama miktarını alacaktır. Bu miktara göre kazanılan puan aşağıdaki gibi hesaplanacaktır:

- Toplam harcama 250'den küçük ise, her 50 TL başına 10p
- Toplam harcama 250 ve 500 arasında ise, her 50 TL başına 15p
- Toplam harcama 500'den büyük ise, her 50 TL başına 20p

Kazanılan puan kullanıcıya iletildikten sonra, bu miktarı TEMA vakfına bağış yapabileceği hakkında kullanıcıya bilgi iletilecek, gelen cevaba göre puan miktarı bağışlanacaktır.

```java
import java.util.Scanner;

public class Main
{
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Lütfen bankamızda şu zamana kadar yapmış olduğunuz toplam harcamayı giriniz: ");
        int spent = sc.nextInt();

        int score;
        if (spent < 250) {
            score = (spent / 50) * 10;
        } else if (spent > 250 && spent < 500) {
            score = (spent / 50) * 15;
        } else {
            score = (spent / 50) * 20;
        }

        System.out.printf("Kazandığınız miktar: %d TL'dir.\n", score);
        System.out.print("Bu miktar ile TEMA vakfına bağışta bulunmak ister misiniz? (y/n): ");
        String decision = sc.next();
        sc.close();

        if (decision.equals("y")) {
            System.out.println("Bağışınız başarıyla gerçekleşmiştir. Teşekkürler. İyi günler dileriz.");
        } else {
            System.exit(0);
        }
    }
}
```

## 1.6 Kullanıcıdan alınan sıra sayısı kadar fibonacci elemanlarını yazdıran program

```java
import java.util.Scanner;

public class Main
{
    public static void main(String[] args) {
       // Değişkenler tanımlandı.
        int fib1 = 1;
        int fib2 = 1;
        int fib;
        // Kullanıcıdan kaçıncı fibonacci dizisi elemanına kadar eleman istediğini belirtmesi amacıyla girdi alındı.
        Scanner sc = new Scanner(System.in);
        System.out.print("İstediğiniz n. fibonacci sayısını belirtiniz:");
        fib = sc.nextInt();
        sc.close();

        // For döngüsü ile elemanları tek tek yazdırıp kullanıcının verdiği sıra sayısı kadar eleman yazdırması amaçlandı.
        for(int i=0; i<fib; i++){
            System.out.print(fib1 + " ");
            /* Aşağıdaki işlemde bir bellek değişkeni atandı.
             * Bu bellek sürekli geçiçi olarak değiştirme usulü bir toplama işlemi hafızasına atıyor.
               Çıktı verip bir sonraki toplamaya geçiyor. */
            int sum = fib1 + fib2;
            fib1 = fib2;
            fib2 = sum;
        }
    }
}
```

## 1.7 Girilen 1 ile 7 arasındaki değere göre hangi günde olduğumuzun çıktısını veren program

```java
import java.util.Scanner;

public class Main
{
    // Girilen 1 ile 7 arasındaki değere göre hangi günde olduğumuzun çıktısını veren program
    public static void main(String[] args) {

        // Değişkenlerimizi tanımlıyoruz.
        int days_index;
        String[] days = "Pazartesi,Salı,Çarşamba,Perşembe,Cuma,Cumartesi,Pazar".split(",");

        // Girdiyi almak için scanner komudumuzu kullanıyoruz.
        Scanner sc = new Scanner(System.in);
        System.out.print("1 ile 7 arasında değer giriniz: ");
        days_index = sc.nextInt();
        sc.close();

        // Kullanıcı girdisini `days` için bir indis olarak kullanıp gün değerini yazdırmaya çalışıyoruz.
        // Eğer kullanıcı 1<=day<=7 aralığında bir sayı vermez ise ArrayIndexOutOfBoundsException'ı
        // yakalıyoruz ve kullanıcıyı bu durum hakkında bilgilendiriyoruz.
        try {
            System.out.printf("Bugün %s\n", days[days_index-1]);
        } catch(java.lang.ArrayIndexOutOfBoundsException ex) {
            System.out.println("Lütfen 1 ile 7 arasında bir değer giriniz!");
        }
    }
}
```
## 1.8 Girilen x ve y değerlerine göre noktanın hangi bölgede bulunduğunun çıktısını veren program
```java
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        //Klavyeden girilen x ve y koordinat noktasına göre koordinatın hangi bölgede yer aldığını bulan program
        int x, y;
        Scanner sc= new Scanner(System.in);
        //x ve y değerlerini istiyoruz.
        System.out.print("Lütfen koordinat sisteminde x'e karşılık gelen sayıyı yazınız:");
        x = sc.nextInt();
        System.out.print("Lütfen koordinat ekseninde y'ye karşılık gelen sayıyı yazınız:");
        y = sc.nextInt();
        sc.close();
        //Koordinat ekseninde sıfırdan büyük veya küçük olma durumuna göre bölge analizi yapıyoruz.
        if (x > 0) {
            System.out.printf("(%d, %d): %d.BÖLGEDEDİR", x, y, ((y>0) ? 1:4));
        } else if (x < 0) {
            System.out.printf("(%d, %d): %d.BÖLGEDEDİR", x, y, ((y<0) ? 3:2));
        } else {
            System.out.printf("(%d, %d): ORİJİNDEDİR", x, y);
        }
    }
}
```
## 1.9 Bir tatlı üretim tesisinde yufka, ceviz ve şeker malzemeleri kullanılarak baklava üretimi yapılmaktadır. Her bir üretim 1 tepsi şeklindedir ve 1 tepsi icin 20 yufka, 3 ceviz ve 5 şeker kullanilir. Her üretim öncesinde eldeki malzemeler kontrol edilerek eğer yeterli ise üretimin yapılmasi, eğer degilse yeni malzeme satın alınıp alınmayacağı sorulur, eğer alınacaksa yeni malzeme miktarları klavyeden girilerek mevcut malzemelere eklenir ve yeniden üretime devam edilir. Eğer üretime devam edilmeyecek ise program sonlandırılır. Yukarıda belirtilen işlemleri aşagıdaki örnek ekran görüntüsüne göre gerçekleştiren java programı
```java
import java.util.Scanner;
import java.util.HashMap;

public class tatlici
{
    private static HashMap<String, Integer> getIngredients(Scanner sc) {
        HashMap<String, Integer> ingredients = new HashMap<String, Integer>();
        String[] ingredient_names = {"yufka", "ceviz", "seker"};
        
        for (int i=0; i<ingredient_names.length; i++) {
            System.out.printf("Lütfen %s miktarını giriniz: ", ingredient_names[i]);
            ingredients.put(ingredient_names[i], sc.nextInt());
        }
        
        return ingredients;
    }
    
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        
        int yufka = 0;
        int ceviz = 0;
        int seker = 0;
        int iter  = 0;
        
        while (true) {
            if (yufka >= 20 && ceviz >= 3 && seker >= 5) {
                yufka -= 20;
                ceviz -= 3;
                seker -= 5;
                iter  += 1;
                
                System.out.printf("%d. üretim gerçekleşti!\n", iter);
            } else {
                System.out.printf("Ürün miktarlarınız (yufka: %d/20, ceviz: %d/3, şeker: %d/5) 1 tepsi için yetersizdir.\n", yufka, ceviz, seker);
                System.out.print("Malzeme eklemek ister misiniz? (E/H): ");
                String decision = sc.next();
                
                switch (decision.toLowerCase()) {
                    case "e":
                        HashMap<String, Integer> ingredients = getIngredients(sc);
                        yufka += ingredients.get("yufka");
                        ceviz += ingredients.get("ceviz");
                        seker += ingredients.get("seker");
                        break;
                        
                    case "h":
                        System.out.println("Daha fazla üretim yapmak istemiyorsunuz, programdan çıkış yapılıyor...");
                        sc.close();
                        System.exit(0);
                        
                    default:
                        System.out.println("Lütfen geçerli bir seçenek giriniz!");
                        break;
                }
            }
        }
    }
}
```
