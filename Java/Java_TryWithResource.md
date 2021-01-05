```
import java.io.FileWriter;
import java.io.IOException;
 
public class TryWithResource {
    public static void main(String[] args) {
        // try with resource statements
        try (FileWriter f = new FileWriter("data.txt")) {
            f.write("Hello");
        } catch(IOException e){
            e.printStackTrace();
        }
    }
}
```
자동으로 close를 하기 때문에 쓸 필요가 없다.  
try()안에 class의 instance를 작성한다.  