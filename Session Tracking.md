Here are your **prepared notes** on **Session Tracking in Servlets** in an **important format**:

**Session Tracking in Servlets**
================================

### **Definition of a Session**

A **session** is the time interval in which two systems communicate with each other. In **HTTP protocol**, the state of communication is **not maintained**. Therefore, **Session Tracking** is used in web applications to maintain the user's state (data).

### **Why Session Tracking is Needed?**

Since HTTP is **stateless**, the web applications must use session tracking techniques to recognize a user across multiple requests.

### **Common Techniques for Session Tracking**

1.  **Cookies**
    
2.  **Hidden Form Fields**
    
3.  **URL Rewriting**
    
4.  **HttpSession (Most Common)**
    

**Cookies & Their Limitations**
-------------------------------

Cookies are small text files stored in the user's browser. However, they have the following **disadvantages**:

*   Can only store **textual information**.
    
*   **Browser dependent**—if disabled, they won’t work.
    
*   Individual cookies can store a maximum of **4KB of data**.
    

**Using HttpSession for Session Tracking**
------------------------------------------

Servlets provide an interface called **HttpSession**, which allows maintaining user sessions across multiple requests.

### **How HttpSession Works?**

1.  The server creates a **unique session ID** for each user.
    
2.  This session ID is sent to the **client** and stored (in a cookie or URL).
    
3.  On subsequent requests, the **client sends the session ID** back to the server.
    
4.  The server retrieves the stored session data.
    

### **Example: Creating a Session in Java Servlet**

  
----------------------------------------

```
import java.io.IOException;
import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import javax.servlet.http.HttpSession;

public class SessionExample extends HttpServlet {
    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        HttpSession session = request.getSession(); // Create session if it doesn't exist

        session.setAttribute("username", "JohnDoe"); // Store session data

        response.getWriter().println("Session Created. User: " + session.getAttribute("username"));
    }
}
```

<img width="734" alt="Screenshot 2025-02-01 at 9 31 45 PM" src="https://github.com/user-attachments/assets/36828346-1ed5-4d08-b3a5-5528c224dcc1" />


**Advantages of HttpSession**
-----------------------------

✔ Works even if cookies are disabled

✔ Can store **objects** (not just text)

✔ Secure, since data is stored on the **server-side**

✔ No size limitation like cookies

**Conclusion**
--------------

**HttpSession** is a powerful way to track user sessions in Java Servlets. Unlike cookies, it allows **storing objects**, works even if cookies are disabled, and provides secure session management.
