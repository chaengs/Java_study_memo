<session & Cookie>  
세션 - 웹 서버 쪽의 웹 컨테이너에 상태를 유지하기 위한 정보를 저장  
쿠키 - 웹 브라우저에 사용자의 상태를 유지하기 위한 정보를 저장  

HTTP 프로토콜은 기본적으로 상태를 저장하지 않음  
request 범위를 넘어선 웹 페이지간의 정보 유지 수단 필요  


Cookie  
클라이언트 브라우저에 정보가 저장되고 HTTP로 전송되므로 탈취될 가능성  
세션의 범위를 넘어 오랜 동안 사용할 수 있음  
사용자가 차단하면 사용할 수 없음  
문자열만 저장 가능  

Session  
javax.servlet.http의 HttpSession 인터페이스  
서버에 정보가 저장되며 상대적으로 안전하게 보관  
쿠키 설정 여부와 상관 없이 사용 가능  
response.encodeURL 사용  
attribute를 통해 문자열 뿐 아니라 객체를 저장 가능  
session scope(세션 영역)에 담은 데이터가 삭제 되는 경우  
1.새로운 요청을 하지 않고 30분이 경과했을 때(기본 시간)  
2.웹브라우저를 닫았을 때  
3.HttpSession 객체의 메소드를 이용해서 강제로 삭제 했을 때  

"nick" 키 값으로 String type 저장하기  
```session.setAttribute("nick", nick);
   req.setAttribute("nick", nick);
```

60초 동안 요청이 없으면 자동 삭제(설정하지 않으면 30분)  ```session.setMaxInactiveInterval(60);```

session scope에 "nick"이라는 키값으로 저장된 String type 읽어오기  
```String nick = (String)session.getAttribute("nick");```

MemberServlet에서 "dto"라는 키값으로 담은 MemberDto 얻어오기  
setAtrribute한 것을 읽어오는 것->getAttribute  
getAttribute() 을 사용시 형변환을 해야함 - 기본 Object 타입    
```MemberDto dto = (MemberDto)request.getAttribute("dto");```

session scope에 "nick"이라는 키값으로 저장된 값 삭제하기  
```session.removeAttribute("nick");```

session scope에 저장된 모든 값 삭제(초기화)하기  
```session.invalidate();```