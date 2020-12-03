-Interface
이름 : 대문자로 시작하고 형용사로 작명
interface에는 method와 변수가 정의 될 수 있음.
interface 내에서 변수에는 값을 지정, method는 구현 내용이 없음.그래서 interface에 작성된 규격에 맞춘 method를 정의, 구혀하는 class가 있어야한다.
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