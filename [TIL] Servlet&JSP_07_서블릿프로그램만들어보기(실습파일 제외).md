# 07. 서블릿 프로그램 만들어 보기

기본 자바 프로그램 : main() 를 기준으로 만든다.

서블릿 프로그램 : service() 를 기준으로 만든다.

```java
public class Nana extends HttpServlet //Nana Servlet
{
	public void service(HttpServletRequest request, HttpServletResponse response) throws IOException, ServletException
{
		//구현 내용
		System.out.println("Hello Servlet");
	}
}

//(WAS) HttpServlet servlet -> (추상클래스)HttpServlet -> service
```

`메모장`+ `JDK` + `톰캣` 을 바로 사용해서 실행해보기