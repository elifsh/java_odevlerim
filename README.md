# java_odevlerim
#### 1-)Math işlevlerini kullanarak parçalı işlevi hesaplayan bir program yazın
```
import java.util.*;
public class dersjava 
{
    public static void main(String[] args) 
    {
        
        double x, y;

        Scanner klavye = new Scanner(System.in);
        x=klavye.nextDouble();
        if (x<0) 
        {
            y = 2.0/3.0*Math.abs(x-1);   
        }
        else if (x>0)
        {
            y = 2.0/3.0*Math.abs(x+1);
        }
        else
        {
            y = Math.sqrt(2.0/3.0);
        }
        System.out.println("Fonksiyon Sonucu:" + y);
        klavye.close();
    }
    
}
```
#### 2-)Bir ondalık sayı (x) giren ve aşağıdaki formüle göre sonucu (y) bularak çıktıda veren programı yazınız.
```
import java.util.*;
public class dersjava 
{
    public static void main(String[] args) 
    {
        
        double x, y;
        
        System.out.println("1 adet x sayısı giriniz:");
        Scanner klavye = new Scanner(System.in);
        x=klavye.nextDouble();

        y=x-(Math.pow(x, 3.0)/3*2) + (Math.pow(x, 5.0)/5*4*3*2) - (Math.pow(x, 7.0)/7*6*5*4*3*2);
        
        System.out.println("Fonksiyon Sonucu:" + y);
        klavye.close();
    }
    
}
```
#### 3-)x'in sıfırdan büyük veya sıfıra küçük eşit olma durumuna göre belirli f(x) ve g(x) fonksiyonlarının ekrana çıktılarını veren programı yazınız.
```
import java.util.*;
public class App 
{
    public static void main(String[] args) throws Exception 
    {   
        double x, fx, gx;
        Scanner klavye = new Scanner(System.in);
        System.out.println("Lütfen bir adet sayı giriniz:");
        x=klavye.nextInt();

        if (x>0) 
        {
            fx = 1.0/(1.0+x);
            gx = 1.0/((x*x)+1.0);

            System.out.println("f(x) değeriniz:" + fx);
            System.out.println("g(x) değeriniz:" + gx);
        }

        else if (x<=0) 
        {
            fx = 1.0/(1.0+(x*x));
            gx = 1.0/(1.0+x+(x*x)+(x*x*x));

            System.out.println("f(x) değeriniz:" + fx);
            System.out.println("g(x) değeriniz:" + gx);
        }
        klavye.close();
    }
}
```
#### 4-)Girilen x değerlerine göre fx değerini hesaplayan programı yazınız.
```
import java.util.*;
public class App 
{
    public static void main(String[] args) throws Exception 
    {   
        double x, fx;
        Scanner klavye = new Scanner(System.in);
        System.out.print("Lütfen bir sayı giriniz:");
        x = klavye.nextDouble();

        if (x<10) 
        {
            fx = Math.abs(x);
        }        
        else if (x >= 10.0 && x<100.0) 
        {
            fx = 3.0/(2.0*x*x);
        }        
        else 
        {
        fx = Math.pow((x-10.0),2.0)/Math.pow(x,3.0); 

        }
        System.out.println("f(x) fonksiyonunun değeri:" + fx);
                
        

        klavye.close();
    }
}
```

