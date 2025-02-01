

**. RequestDispatcher (Server-Side Forward)**
---------------------------------------------

### **Definition:**

*   It **forwards** the request from one servlet (or JSP) to another **on the server side** without changing the URL in the browser.
    
*   The client **does not know** about this internal forwarding.
    

### **Syntax:**

```
RequestDispatcher rd = request.getRequestDispatcher("targetPage.jsp");
rd.forward(request, response);
```
### **How It Works:**

1.  The **original request** is forwarded to another resource.
    
2.  **Control stays on the server** (client doesn’t see the new URL).
    
3.  **Data from the request is retained**.

```
RequestDispatcher rd = request.getRequestDispatcher("dashboard.jsp");
rd.forward(request, response);
```
If a request comes to LoginServlet and is forwarded to dashboard.jsp, the browser URL remains /LoginServlet.


*   If a request comes to LoginServlet and is forwarded to dashboard.jsp, the browser URL **remains** /LoginServlet.
    

### **Use Case:**

*   When you want to **pass data** from one resource to another **without** exposing the internal structure to the client.
    

### **Key Features:**

✔ **Faster** (happens inside the server)
.✔ **Same request object is used** (data is preserved).
✔ **Client URL remains unchanged**.
✔ **Better for intra-application navigation**.


**2. sendRedirect (Client-Side Redirect)**
-------------------------------------------

### **Definition:**

*   It **redirects** the client to another resource **by sending a new HTTP response** with a Location header.
    
*   The **browser makes a new request**, and the URL **changes**.
    

### **Syntax:**


```
response.sendRedirect("https://example.com/newPage.jsp");
```

### **How It Works:**

1.  The server sends an **HTTP response** with a new URL.
    
2.  The **browser makes a new request** to the given URL.
    
3.  **The previous request data is lost** because it's a new request.



<img width="714" alt="Screenshot 2025-02-01 at 10 44 46 PM" src="https://github.com/user-attachments/assets/b80ef333-745c-4bea-8d30-113672529ff2" />



**Which One to Use?**
---------------------

🔹 **Use RequestDispatcher** when:

*   You need to pass request attributes.
    
*   You want to keep the **URL unchanged**.
    
*   The navigation is **within the same application**.
    

🔹 **Use sendRedirect** when:

*   You want to redirect to an **external URL**.
    
*   You want to **change the browser’s URL**.
    
*   You don’t need to keep request data.




### **Real-World Example**

#### **1️⃣ Using RequestDispatcher**

Imagine you have a login page, and after successful authentication, you want to **forward** the request to dashboard.jsp **without changing the URL**.

```
if(authenticated) {
    RequestDispatcher rd = request.getRequestDispatcher("dashboard.jsp");
    rd.forward(request, response);
} else {
    out.println("Invalid credentials");
}
```

*   The URL remains login.jsp, but the content is from dashboard.jsp.
    

#### **2️⃣ Using sendRedirect**

If you want to **redirect** users to a different domain (e.g., Google login):
```
response.sendRedirect("https://accounts.google.com/");
```
*   The **browser URL changes**, and the user is sent to **Google login**.
    

### **Conclusion**

*   **Use RequestDispatcher for internal forwards (better performance, retains data).**
    
*   **Use sendRedirect for external navigation or when you want to change the URL.** 🚀









<img width="912" alt="Screenshot 2025-01-21 at 1 25 44 PM" src="https://github.com/user-attachments/assets/ba766e60-74e4-479b-ab62-623b2bf42f8b" />

<img width="767" alt="Screenshot 2025-01-21 at 1 25 57 PM" src="https://github.com/user-attachments/assets/73e8d594-5198-43ea-be41-6619592a0338" />


<img width="928" alt="Screenshot 2025-01-21 at 1 26 10 PM" src="https://github.com/user-attachments/assets/7deb5f15-8c96-43b5-bbc0-8158d0482f95" />


<img width="802" alt="Screenshot 2025-01-21 at 1 26 30 PM" src="https://github.com/user-attachments/assets/e0ea6b94-f110-472e-9e57-2c6afc7046d6" />


<img width="864" alt="Screenshot 2025-01-21 at 1 28 06 PM" src="https://github.com/user-attachments/assets/ca2f0738-be33-43f4-b65e-56d21d0fcd47" />
