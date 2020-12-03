-생성자가 있는 클래스를 상속할 때 상위 클래스의 생성자를 실행해야 한다.
```
class Cal{
    int v1,v2;
    Cal(int v1, int v2){
        System.out.println("Cal init!!");
        this.v1 = v1; this.v2 = v2;
    }
    public int sum(){return this.v1+v2;}
}
class Cal3 extends Cal{
    Cal3(int v1, int v2) {
        super(v1, v2);
    }
```

-'생성자'는 초기에 주입/수행해야되는 값이 있을 때 사용한다.
-'this'는 instance를 가르킨다.
