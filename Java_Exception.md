부모 exception은 자식 exception을 포괄한다.  
```
public class ExceptionApp {
    public static void main(String[] args) {
        System.out.println(1);
        int[] scores = {10,20,30};
        try {
            System.out.println(2);
            System.out.println(scores[3]);
            System.out.println(3);
//            System.out.println(2 / 0);
            System.out.println(4);
        } catch(ArithmeticException e){
            System.out.println("계산이 잘못된 것 같아요.");
        } catch(Exception e){
            System.out.println("먼가 이상합니다. 오류가 발생했습니다. ");
        }
        System.out.println(5);
    }
}
```
try, catch문을 써서 예외 처리를 한다.  
먼저 쓰인 순서대로 우선순위가 부여되기 때문에 코드를 짤 때 무엇을 우선으로 둘 지 생각해야 한다.  
try문 중간에 exception이 실행되면 그 아래에 코드가 있어도 더 이상 실행되지 않는다.   
exception이 발생하면 바로 try문을 빠져나간다.  

```
catch(ArithmeticException e){
            System.out.println(e.getMessage());
            e.printStackTrace();
}
```
printStackTrace : 어디서 에러가 발생했는지 알려주는 메소드. (사용자에게 보여주지 않는다.)  

예외처리를 필수적으로 해야 하는 checked exception과 선택적으로 하면 되는 unchecked exception이 있다.  
