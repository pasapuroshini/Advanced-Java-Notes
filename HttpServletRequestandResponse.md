Servlet Lifecycle and Request/Response Objects
==============================================

Servlet Lifecycle
-----------------

1.  **Initialization (init method):**
    
    *   Called once when the servlet is first loaded.
        
    *   Used to perform any one-time setup or resource allocation.
        
2.  **Service (service method):**
    
    *   Handles client requests and generates responses.
        
    *   Receives two important objects:
        
        *   **HttpServletRequest**: Contains client request data.
            
        *   **HttpServletResponse**: Used to send response data back to the client.
            
3.  **Destruction (destroy method):**
    
    *   Called when the servlet is being removed from service.
        
    *   Used to release resources.
        

Request and Response Objects
----------------------------

### HTTP Request Object

*   **Purpose:**
    
    *   Contains all data sent from the client to the server.
        
    *   Examples of data:
        
        *   Query parameters (e.g., num1 and num2 for addition).
            
        *   Client information (e.g., IP address, browser details).
            
*   **Lifecycle:**
    
    *   Automatically created by the server (e.g., Tomcat) when a client sends a request.
        
    *   Passed to the servlet’s service method.
        
*   **Key Features:**
    
    *   Stores request data in an object-oriented format.
        
    *   Provides methods to extract data (e.g., getParameter(String name)).
        

### HTTP Response Object

*   **Purpose:**
    
    *   Contains data to be sent back to the client.
        
    *   Examples of data:
        
        *   Simple text (e.g., "Result is 5").
            
        *   HTML, images, videos, or JSON responses.
            
*   **Lifecycle:**
    
    *   Automatically created by the server when the servlet processes a request.
        
    *   Passed to the servlet’s service method.
        
*   **Key Features:**
    
    *   Allows specification of:
        
        *   Content type (e.g., text/plain, text/html, application/json).
            
        *   Response data via methods like getWriter().
            

How Request and Response Objects Work
-------------------------------------

1.  **Client to Server Communication:**
    
    *   A client sends a request to the servlet.
        
    *   The request includes data like parameters (num1, num2) and client metadata.
        
    *   This data is encapsulated in the HttpServletRequest object.
        
2.  **Processing by the Servlet:**
    
    *   The servlet accesses the request data via the HttpServletRequest object.
        
    *   Performs required operations (e.g., adding two numbers).
        
3.  **Server to Client Communication:**
    
    *   The servlet prepares a response.
        
    *   Data is encapsulated in the HttpServletResponse object.
        
    *   The server sends the response back to the client.
        

Notes on Implementation
-----------------------

*   **Automatic Object Creation:**
    
    *   HttpServletRequest and HttpServletResponse objects are created by the server (e.g., Tomcat).
        
    *   Developers only use the provided references in the service method.
        
*   **Interfaces:**
    
    *   HttpServletRequest and HttpServletResponse are interfaces.
        
    *   Their implementation is provided by the server.
        
*   **Content Types:**
    
    *   Specify the type of response data using setContentType(String type).
        
    *   Examples:
        
        *   text/plain for plain text.
            
        *   text/html for HTML content.
            
        *   application/json for JSON data.
            

Example Scenario: Adding Two Numbers
------------------------------------

1.  **Client Request:**
    
    *   Client sends a request to add 2 and 3.
        
    *   Parameters num1=2 and num2=3 are included in the request.
        
2.  **Server Processing:**
    
    *   The servlet retrieves num1 and num2 from the HttpServletRequest object.
        
    *   Calculates the sum (5).
        
3.  **Response:**
    
    *   The servlet sends the result (5) back to the client in the HttpServletResponse object.
        

Calling One Servlet from Another
--------------------------------

*   **Scenario:** Servlet S1 wants to call servlet S2.
    
*   **Steps:**
    
    1.  S1 receives a client request.
        
    2.  S1 forwards the request to S2 using the RequestDispatcher.
        
    3.  S2 processes the forwarded request and generates a response.
        
    4.  The response is sent back to the client.
