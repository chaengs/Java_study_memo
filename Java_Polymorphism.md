<다형성>  
```
interface Calculable{
	double Pi = 3.14;
	int sum(int v1, int v2);
}

interface Printable{
	void print();
}

class RealCal implements Calculable, Printable{
	public int sum(int v1, int v2) {
		return v1+v2;
	}
	public void print() {
		System.out.println("Print");
	}
}

public class InterfaceApp {

	public static void main(String[] args) {
		RealCal c = new RealCal();
		System.out.println(c.sum(1,2));
		c.print();
		System.out.println(c.Pi);

	}

}

```
c의 data type인 RealCal 외에도 RealCal class가 구현하고 있는 interface(Calculable, Printable)로 지정할 수 있다.  
```
Calculable c = new RealCal();
```
이렇게 하게 되면 Printable의 print() method는 접근 할 수 없다.  
RealCal class에서 필요한 기능이 있는 interface만 이용하겠다고 명시할 수 있다.  
data type에서 interface를 지정하면 같은 interface를 구현하고 있는 어떤 class든 올 수 있다.  