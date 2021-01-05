post method가 url에 value 값등 줄줄이 달지 않기 때문에 깔끔하다.   
그래서 post를 많이 사용한다.  
```<form action="send" method="post">```
```<form action="send.jsp" method="get">```
  
  
문자열을 int type으로 바꾸는 method  
```int num = Integer.parseInt(request.getParameter("num"));```
  
application 전역에 대해서 Dao 객체는 오직 한 번만 생성되는 구조로 바꾸어야 한다.  
어플리케이션은 여러 client의 요청을 빠르게 처리 해야 하기 때문에 불필요한 Dao의 중복 생성은 web application 성능에 영항을 준다.  
```
public class TodoDao {
	//1.자신의 객체를 담을 static 필드 선언
	private static TodoDao dao;
	//2.외부에서 객체 생성이 불가 하도록 생성자의 접근 지정자를 private로 설정
	private TodoDao() {}
	//3.자신의 참조값을 리턴해주는 public static 메소드 정의
	public static TodoDao getInstance() {
		if(dao==null) {//getInstance() 메소드가 최초 호출되는 경우
			dao = new TodoDao(); //객체를 생성해서 참조값을 static 필드에 저장한다.
		}
		//static 필드에 저장된 참조값을 리턴해준다.
		return dao;
	}
```