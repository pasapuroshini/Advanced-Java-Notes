# Servlet with Annotation
- The Servlet life cycle will be managed by the Servlet container that is under the Web/Application server.
- Whenever an HttpRequest comes from the client browser, the servlet container will map the request to the corresponding servlet based on the URL mappings provided in the deployment descriptor file – web.xml

  ```
  <servlet>
  <servlet-name>Hello Servlet</servlet-name>
  <servlet-class>Hello Servlet</servlet-class>
  </servlet>

  <servlet-mapping>
  <servlet-name>HelloServlet</servlet-name>
  <url-pattern>/hello</url-pattern>
  </servlet-mapping>
  
  ```
-Here, whenever there is a “/hello” URL coming from the client request, we are mapping it to the “HelloServlet” class. Instead of providing these mappings in the web.xml file, we can simply provide an annotation in the Servlet as below,


  ```
@WebServlet("/hello") 
public class HelloServlet extends HttpServlet { 
    // Code to be executed... 
}
```



# Example 1:
index.html
```
<!DOCTYPE html>
<html>
<head>
<meta charset="ISO-8859-1">
<title>Home</title>
</head>
<body>
<form action="hello" method="post">
Welcome Page:<input type="submit"/>
</form>
</body>
</html>

```

Html pags which maps the servlet with url "/hello"

```
import java.io.IOException; 
import java.io.PrintWriter; 
import javax.servlet.ServletException; 
import javax.servlet.annotation.WebServlet; 
import javax.servlet.http.HttpServlet; 
import javax.servlet.http.HttpServletRequest; 
import javax.servlet.http.HttpServletResponse; 
  
@WebServlet("/hello") 
public class HelloServlet extends HttpServlet { 
    private static final long serialVersionUID = 1L; 
  
    protected void doPost(HttpServletRequest request, 
                          HttpServletResponse response) 
        throws ServletException, IOException 
    { 
  
        // set the response content type 
        response.setContentType("text/html"); 
        PrintWriter out = response.getWriter(); 
  
        // Print hello message to the client browser in 
        // response object 
        out.println( 
            "<h3>Hello, Welcome to GeeksforGeeks!!</h3>"); 
        out.close(); 
    } 
}
```
-When user clicks submit for the welcome page, container will process the “@WebServlet(“/hello”)” annotation and maps the “HelloServlet” class.

-As the method is mentioned as “post” in Html page, container will execute “doPost()” method in “HelloServlet” class.




