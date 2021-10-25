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
            y = 2/3*Math.abs(x-1);   
        }
        else if (x>0)
        {
            y = 2/3*Math.abs(x+1);
        }
        else
        {
            y = Math.sqrt(2/3);
        }
        System.out.println("Fonksiyon Sonucu:" + y);
        klavye.close();
    }
    
}
```


