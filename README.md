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
#### 1-)Bir ondalık sayı (x) giren ve aşağıdaki formüle göre sonucu (y) bularak çıktıda veren programı yazınız.
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


