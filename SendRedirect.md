
**Servlet Response Redirection (sendRedirect() Method) **
==============================================================

**What is a Servlet?**
----------------------

*   A **Servlet** is a Java program that runs on the **server-side** and generates **dynamic responses** to client requests.
    
*   It **accepts requests** from the browser, **processes them**, and **generates responses**.
    

**Need for Response Redirection**
---------------------------------

Sometimes, a servlet **needs to call another servlet or redirect to a different server**. For example:

1.  **Online Shopping:** Redirecting users from a shopping website to a **payment gateway**.
    
2.  **Online Education Platforms:** Redirecting users to **Google Search or another website** for additional information.
    

To achieve this, Java Servlets provide the **sendRedirect()** method.




**HttpServletResponse Interface**
---------------------------------

The **HttpServletResponse** interface extends **ServletResponse** and provides **HTTP-specific** functionalities such as:

*   **Modifying HTTP headers**
    
*   **Setting cookies**
    
*   **Redirecting responses**
    

**Understanding sendRedirect()**
--------------------------------

The **sendRedirect()** method is used to **redirect the client to another URL**.

*   It sends an **HTTP response** with **status code 302 (Found)** and a new **Location header**.
    
*   The browser then makes a **new request** to the redirected URL.


## Creating a simple servlet that will redirect the page to another website.

### index.html


<img width="978" alt="Screenshot 2025-02-01 at 9 44 18 PM" src="https://github.com/user-attachments/assets/7716fbe3-88f8-4022-8b62-c4b9bd70e9e3" />



### ServletRedirect.java




<img width="1033" alt="Screenshot 2025-02-01 at 9 45 06 PM" src="https://github.com/user-attachments/assets/c6629551-5545-4f13-80e0-e8b356dd48f1" />

### Output

<img width="701" alt="Screenshot 2025-02-01 at 9 45 59 PM" src="https://github.com/user-attachments/assets/e8aefdc7-2c4b-4f1a-bc0c-a1e4d6f536b9" />

<img width="545" alt="Screenshot 2025-02-01 at 9 46 19 PM" src="https://github.com/user-attachments/assets/26e60596-9682-4eb1-90c6-708ecfb7b0ab" />


-We need to import all the required packages from javax.servlet. Instead of mapping the page with servlet in web.xml, we are specifying it using annotation – @WebServlet(“/redirect”). When the ‘doGet’ method executes, the response will redirect to the specified URL.












<img width="937" alt="Screenshot 2025-01-21 at 3 24 35 PM" src="https://github.com/user-attachments/assets/72c0d238-67c0-48ef-8005-1e76ddf2f40f" />
<img width="925" alt="Screenshot 2025-01-21 at 3 24 50 PM" src="https://github.com/user-attachments/assets/73710351-6ad4-4adf-904e-62358d6e3423" />
