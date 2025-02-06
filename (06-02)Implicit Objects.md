# Implicit Objects in JSP
## JSP :
-JSP stands for Java Server Pages, and it’s a server side technology.
-It’s used for creating web applications and dynamic web content. 
-The main property of JSP is that we can insert our java code inside our HTML page using JSP tag. JSP provides you platform-independent pages.


 ## Implicit Objects
 Implicit Objects are set of Java objects that JSP Container makes available to developers on each page.
 
 These objects may be accessed as built-in variables via scripting elements and can also be accessed programmatically by JavaBeans and Servlets.JSP provide you Total 9 implicit objects which are as follows.

request: This is the object of 'HttpServletRequest' class associated with the request.

response: This is the object of  'HttpServletResponse' class associated with the response to the client.

-config: This is the object of `ServletConfig` class associated with the page.

-application: This is the object of `ServletContext` class associated with the application context.

-session: This is the object of `HttpSession` class associated with the request.

-page context: This is the object of `PageContext` class that encapsulates the use of server-specific features. This object can be used to find, get or remove an attribute.

-page object: The manner we use the keyword this for current object, `page object` is used to refer to the current translated servlet class.

-exception: The exception object represents all errors and exceptions which is accessed by the respective jsp. The exception implicit object is of type java.lang.Throwable.

-out: This is the PrintWriter object where methods like print and println help for displaying the content to the client.
- 
# Advantage of JSP over servlet
Servlets are difficult to code than JSP.

In another way, we can say, JSP is the replacement for Servlets.

In Servlets, both static code and dynamic code are put together. 

In JSP, they are separated.

The objects of PrintWriter, ServletConfig, ServletContext, HttpSession and RequestDispatcher etc. are created by the Programmer in Servlets. But in JSP, they are built-in and are known as implicit objects.



##  Disadvantage : 
 

JSP pages require more memory to hold the page.

The output is in HTML which is not rich for viewers.



















