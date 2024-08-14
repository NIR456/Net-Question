### Understanding Services and Dependency Injection (DI) in ASP.NET Core:-
**Services:-** In ASP.NET Core, services are components that provide functionality to our application, like logging, configuration, data access, etc. 

**DI :-** Dependency Injection (DI) is a technique to achieve Inversion of Control (IoC) between classes and their dependencies. DI makes your application more modular, testable, and maintainable.

**Types of Services in ASP.NET Core**
##### Transient Services 
- **Description:** Created each time they are requested.
- **Use Case:** Suitable for lightweight and stateless services.

##### Scoped Services
- **Description:** Created once per request.
- **Use Case:** Useful for services that maintain state within a request.

##### Singleton Services
- **Description:** Created once for the application's lifetime.
- **Use Case:** Suitable for stateful and globally accessible services.

**Types of Dependency Injection in ASP.NET Core**

#### 1. Constructor Injection

Constructor Injection is the most common form of dependency injection. Dependencies are provided through the class constructor.

#### 2. Property Injection in ASP.NET Core

Property Injection involves setting dependencies through public properties. This can be useful for optional dependencies that can be set after the object is constructed.
#### 3. Method Injection in ASP.NET Core

Method Injection involves passing dependencies directly to a method. This can be useful when dependencies are needed only for a specific method.


 **CORS Policy in ASP.NET Core**

CORS (Cross-Origin Resource Sharing) is a security feature implemented by web browsers to control how web pages can make requests to different domains. In ASP.NET Core, you can configure CORS to allow or restrict cross-origin requests.

## What is CORS?

CORS allows servers to specify which domains are permitted to access resources on the server. This is essential for web security, as it helps prevent unauthorized access to resources.

## Agile Methodology

- Agile is an iterative software development methodology that helps developers create and deliver applications more quickly and efficiently. It is based on the principles of collaboration, customer feedback, and the “three C's” – card, conversation, and confirmation.

- Agile is a software development methodology that is becoming more popular every day. It defines the mind set of many software development teams working across the globe.

  - Link For Details (https://www.geeksforgeeks.org/software-engineering-agile-software-development/)

### What is a scrum in software development

- Scrum is a popular framework that is used whenever we want to develop complex products, Ken Schwaber and Jeff Sutherland are known as the people who developed Scrum. Scrum is a type of Agile framework.
- Scrum is a management framework that teams use to self-organize tasks and work towards a common goal. It is a framework within which people can address complex adaptive problems while the productivity and creativity of delivering products are at the highest possible value. Scrum is a management framework that teams use to self-organize and work towards a common goal.

- Scrum allows us to develop products of the highest value while making sure that we maintain creativity and productivity.
- The iterative and incremental approach used in scrum allows the teams to adapt to the changing requirements.
  ##### Read (https://www.geeksforgeeks.org/scrum-software-development/)


## Unit testing
   - Unit testing is a crucial practice in ASP.NET Core for ensuring the quality and reliability of your application. It involves testing individual units of code (like 
     controllers, services, or models) in isolation from other parts of the application and external dependencies.

   ##### Here's a deeper dive into unit testing in ASP.NET Core:

   #### Why Unit Test?

   - Catches bugs early: Unit tests help identify issues early in the development process, preventing them from propagating to later stages.
    Improves code maintainability: Well-written unit tests clarify the intended behavior of your code, making it easier to understand and modify in the future.
    Increases confidence in code changes: With unit tests in place, you can make code changes with more confidence, knowing that the existing functionalities remain intact.
   Popular Unit Testing Frameworks:

   - ASP.NET Core offers flexibility in choosing a unit testing framework. Here are some widely used options:

   - xUnit: A free, open-source, and easy-to-use framework with a concise syntax for writing tests.
   - NUnit: Another popular open-source framework with a mature feature set and support for various testing paradigms.
   - MSTest: A built-in unit testing framework from Microsoft, well-integrated with Visual Studio.
   - 
## data Stracture
   - A data structure is a specialized format for organizing, processing, retrieving and storing data. There are several basic and advanced
     types of data structures, all designed to arrange data to suit a specific purpose.
     
   - The data structure name indicates itself that organizing the data in memory. There are many ways of organizing the data in the memory as we have already seen one of 
     the data structures, i.e., array in C language. Array is a collection of memory elements in which data is stored sequentially, i.e., one after another. In other words, 
     we can say that array stores the elements in a continuous manner. This organization of data is done with the help of an array of data structures. There are also other 
     ways to organize the data in memory. Let's see the different types of data structures.
   - The data structure is not any programming language like C, C++, java, etc. It is a set of algorithms that we can use in any programming language to structure the data 
     in the memory.

   - To structure the data in memory, 'n' number of algorithms were proposed, and all these algorithms are known as Abstract data types. These abstract data types are the 
     set of rules.
     - Link For Details (https://www.javatpoint.com/data-structure-tutorial)
     
     

## Repository in asp .Net core
  -The Repository pattern is a design pattern that isolates data access logic from the business logic. It provides a way to manage data access so that the underlying data 
    source can be changed without impacting the business logic.
  - The repository design pattern is a specific type of design pattern that deals with data access. It provides an abstraction over the data layer, making your application 
    more modular and easier to test. Here’s how it works in ASP.NET Core.
    **In ASP.NET Core, there are several types of repositories that you can implement depending on your needs and the complexity of your application. Here are some common 
   types:**
  ### 1. Generic Repository
      
  ### 2. Specific Repository
      
  ### 3. Unit of Work with Repository
     

     Ans 1. A Generic Repository provides a single class with methods that can be used for any entity type. This reduces code duplication and provides a more generic data 
            access solution.
            ```public interface IGenericRepository<T> where T : class
               {
                 IEnumerable<T> GetAll();
                 T GetById(int id);
                 void Add(T entity);
                 void Update(T entity);
                 void Delete(int id);
              }
           ```
           Ans 2. A Specific Repository is tailored for a particular entity. This allows for custom methods that are specific to the entity and not part of the generic 
                  repository.
                  ```
                   ####Interface
                    public interface IProductRepository : IGenericRepository<Product>
                    {
                      IEnumerable<Product> GetProductsByCategory(int categoryId);
                    }
                    ####Implementation
                    public class ProductRepository : GenericRepository<Product>, IProductRepository
                     {
                      public ProductRepository(ApplicationDbContext context) : base(context)
                     {
                   }

                   public IEnumerable<Product> GetProductsByCategory(int categoryId)
                      {
                   return _context.Products.Where(p => p.CategoryId == categoryId).ToList();
                  }
                  }
                  ```

## Design patterns
### Design patterns are general, reusable solutions to common problems in software design. They are templates designed to help you write code that is easier to understand, maintain, and extend. Some common design patterns include.
 - **Singleton:-** Ensures a class has only one instance and provides a global point of access to it.
 - **Factory:-** Creates objects without specifying the exact class of object that will be created.
 - **Observer:-** Defines a one-to-many dependency between objects so that when one object changes state, all its dependents are notified.
## Docker
 - Docker is a platform and a tool that allows you to build, distribute, and run applications inside containers. It's designed to make it easier to create, deploy, and run applications by using containers. Containers allow a developer to package up an application with all parts it needs, such as libraries and other dependencies, and ship it all out as one package.
   ### Docker Container:-
    - A Docker container is a lightweight, standalone, executable package of software that includes everything needed to run an application: code, runtime, system tools, system libraries, and settings. Containers isolate software from its surroundings, for example, differences between development and staging environments and help reduce conflicts between teams running different software on the same infrastructure.
   ### Docker Image:-
    - A Docker image is a read-only template that contains a set of instructions for creating a Docker container. It provides a complete and executable package of an application, which includes everything needed to run an application - the code, runtime, libraries, environment variables, and configuration files. Images are used to create Docker containers, and they can be built by following a set of instructions (called a Dockerfile) or can be pulled from a Docker registry like Docker Hub. 
## Kubernetes:-
- Kubernetes (K8s) is an open-source container orchestration platform designed to automate the deployment, scaling, and management of containerized applications. It helps in running distributed systems resiliently and efficiently.
## Lazy Loading
- Lazy loading in Entity Framework Core allows related data to be loaded automatically when it is accessed for the first time. This can be beneficial for performance when you do not need all related data initially but want it to be available if needed
````
  public class Blog
  {
    public int BlogId { get; set; }
    public string Url { get; set; }
    
    // Navigation property
    public virtual ICollection<Post> Posts { get; set; }
  }

  public class Post
 {
    public int PostId { get; set; }
    public string Title { get; set; }
    public string Content { get; set; }
    
    // Foreign key
    public int BlogId { get; set; }
    
    // Navigation property
    public virtual Blog Blog { get; set; }
  }
````
##### Example 2
````
  using (var context = new BloggingContext())
 {
    // Load a blog
    var blog = context.Blogs.First();
    
    // The related posts are not loaded yet
    Console.WriteLine("Blog loaded");
    
    // Access the Posts property to trigger lazy loading
    var posts = blog.Posts;
    
    Console.WriteLine($"Number of posts: {posts.Count}");
 }
````
##  Synchronous And Asynchronous Programming
  - In synchronous programming, code execution happens sequentially. Each statement waits for the previous one to complete before executing. This can lead to blocking, 
   where a long-running operation prevents further code execution until it finishes.
   **Examples**
   ````
    using System;
    using System.Net.Http;
    class Program
      {
        static void Main()
        {
          var data = GetData();
          Console.WriteLine(data);
        }
       static string GetData()
       {
        using (var client = new HttpClient())
        {
            var response = client.GetStringAsync("https://api.example.com/data").Result;
            return response;
        }
       }
      }
   ````
  - In asynchronous programming, code can continue executing without waiting for a long-running operation to complete. This is 
    achieved using the async and await keywords 
    in C#. The async keyword indicates that a method is asynchronous, and await is used to suspend the execution of an asynchronous 
    method until the awaited task 
    completes.
      ** Examples**
     ````
      using System;
      using System.Net.Http;
      using System.Threading.Tasks;

       class Program
       {
        static async Task Main()
      {
        var data = await GetData();
        Console.WriteLine(data);
     }

      static async Task<string> GetData()
     {
        using (var client = new HttpClient())
        {
            var response = await client.GetStringAsync("https://api.example.com/data");
            return response;
        }
     }
     }
     ````


## Extension Method in C#
 - Extension methods in C# allow us to add new methods to existing types without modifying their source code. They are a powerful feature that enhances the flexibility and 
   readability of your code. Here’s how you can create and use an extension method.
    ### Creating an Extension Method
     #### 1. Define a Static Class: Extension methods must be defined in a static class.
     #### 2. Create a Static Method: The extension method itself must be static.
     #### 3. Use the this Keyword: The first parameter of the method specifies the type it extends and must be preceded by the this keyword.
      - Let's create an extension method for the string class that checks if a string is a valid email address.
        Define the Static Class:-
        ````
            public static class StringExtensions
            {
               public static bool IsValidEmail(this string email)
           {
             return email.Contains("@") && email.Contains(".");
          }
           }
        ````
        Using the Extension Method:-
        ````
          class Program
           {
            static void Main()
             {
               string email = "example@example.com";
                bool isValid = email.IsValidEmail(); // Using the extension method
                Console.WriteLine(isValid); // Outputs: True
            }
          }
       ````
## constant and Enum
  ###  Enum (Enumeration)
  - Purpose: Enums are used to represent a group of related named constants, typically to define a type that can take one of a fixed set of values.
  - Type: Enum types are value types derived from System.Enum.
  - Underlying Type: The default underlying type is int, but you can specify a different integral type (byte, sbyte, short, ushort, uint, long, or ulong).
  - Usage: Enums are ideal for representing a collection of related values, such as days of the week, error codes, or states.
     ````
       public enum DaysOfWeek
       {
         Sunday,
         Monday,
         Tuesday,
         Wednesday,
         Thursday,
         Friday,
        Saturday
      }
       // Usage
       DaysOfWeek today = DaysOfWeek.Monday;
     ````
 ### Constant
  - urpose: Constants are used to define immutable values that do not change for the lifetime of the application.
  - Type: Constants can be of any basic type (e.g., int, float, string).
  - Value Assignment: Constants must be assigned a value at the time of declaration, and that value cannot be changed later.
  - Usage: Constants are ideal for defining values that are not expected to change, such as mathematical constants, configuration values, or fixed values used throughout 
    the application.
       ````
          public class Constants
          {
            public const int MaxItems = 100;
            public const string ApplicationName = "MyApp";
          }
          // Usage
          int max = Constants.MaxItems;
          string appName = Constants.ApplicationName;
       ````
## Readonly and Constant Difference
  - In C#, readonly and const are used to define fields that should not be modified after they are initialized, but they serve slightly different purposes and have 
    different behaviors.
    
     **Const**
      - Compile-time constant: The value must be known at compile time and cannot be changed after it is defined.
        
    **readonly**
     - Runtime constant: The value can be assigned either at the time of declaration or in the constructor of the class. This allows for different instances of the class to 
       have different values for the readonly field.
  ## Filter and types
   - In ASP.NET Core, filters are used to run code before or after certain stages in the request processing pipeline. They can be used to handle cross-cutting concerns such 
     as authorization, caching, exception handling, and logging. There are several types of filters:-
     
   ### Types Of filter:-
  #### Authorization Filter: Validate user credentials.
       - Run before anything else and are used to determine whether the user is authorized to perform the current request.
  #### Resource Filter: Control execution order, caching.
        - Run after authorization but before model binding, and they can short-circuit the request processing pipeline.
  #### Action Filter: Pre/post processing of action methods.
        - Run before and after the action method execution.
  #### Exception Filter: Handle exceptions globally.
        - Run when an exception occurs during the action method execution.
  #### Result Filter: Modify or handle action results.
        - Run before and after the action result is executed.
        
## SOLID Principle
 - The SOLID principles are a set of five design principles intended to make software designs more understandable, flexible, and maintainable. They are especially useful in 
 object-oriented programming and are widely used in ASP.NET Core development.
  **SOLID Principles**
    ### Single Responsibility Principle (SRP)
      - A class should have only one reason to change, meaning it should have only one job or responsibility.
        ````
         public class Invoice
         {
           public void CalculateTotal() 
           {
             // Code to calculate the total amount of the invoice
           }
           public void PrintInvoice()
           {
            // Code to print the invoice
           }
         }
         - Issue: The Invoice class has two responsibilities: calculating the total and printing the invoice.
         Correct Example :-
           public class Invoice
            {
                public void CalculateTotal() 
                 {
                   // Code to calculate the total amount of the invoice
                }
            }

          public class InvoicePrinter
           {
             public void Print(Invoice invoice)
             {
              // Code to print the invoice
             }
          }
        ````
    ### Open/Closed Principle (OCP) - Extend behavior without modifying code.
      -  Software entities should be open for extension but closed for modification.
        
        `````
           public class Shape
           {
             public double CalculateArea(object shape)
              {
                if (shape is Rectangle)
                 {
                   Rectangle rectangle = (Rectangle)shape;
                   return rectangle.Width * rectangle.Height;
                 }
               else if (shape is Circle)
               {
                Circle circle = (Circle)shape;
                return Math.PI * circle.Radius * circle.Radius;
              }
             else
             {
               throw new ArgumentException("Unknown shape");
             }
             }
           }
           public class Rectangle
           {
             public double Width { get; set; }
             public double Height { get; set; }
           }
          public class Circle
           {
            public double Radius { get; set; }
           }
          - Issue: To add a new shape, you would need to modify AreaCalculator.
       `````
    ### Liskov Substitution Principle (LSP)
      - Objects of a superclass should be replaceable with objects of a subclass without affecting the functionality.
        ````
          public class Bird
           {
             public virtual void Fly() { }
           }
          public class Sparrow : Bird
          {
            public override void Fly()
          {
           // Sparrow flying code
          }
         }
         public class Ostrich : Bird
         {
            public override void Fly()
         {
           // Ostrich cannot fly
            throw new NotImplementedException();
        }
      }
     -Issue: The Ostrich class violates LSP because it cannot fly.
        ````
    ### Interface Segregation Principle (ISP)
      - No client should be forced to depend on methods it does not use.
    ### Dependency Inversion Principle (DIP)
      - High-level modules should not depend on low-level modules. Both should depend on abstractions.

## Interface
  - An interface in C# is a way to define a contract or a set of methods and properties that a class must implement. Interfaces do not contain any code themselves; they 
    only specify what methods or properties should be included in the implementing class.
    
    **Why Use Interfaces?**
    ### 1. Define a Contract: Interfaces allow you to define a set of methods and properties that any class can implement. This ensures that different classes can be used interchangeably if they follow the same contract.
            
    ### 2. Multiple Inheritance: Classes can implement multiple interfaces, which provides a way to combine different sets of functionality.

## Routing in .Net Core
 - Routing is a pattern-matching system that monitors the incoming request and figures out what to do with that request. Typically, it is a way to serve the user's request.
 - When a user request URLs from the server then URLs are handled by the routing system. The Routing system tries to find out the matching route pattern of the required Url 
   with already registered routes which are map to controller, actions, files, or other items. If there is a matching route entry, then it processes the request i.e. serves 
   the resource, otherwise, it returns a 404 error.
 - In our .NET Core project, we utilize Ocelot as our API Gateway to manage and route requests to various downstream microservices. This allows us to abstract the client 
   from the complexity of our backend services and apply cross-cutting concerns at a single entry point.    
## Meddleware ( types and desription)
 - Middleware is a powerful tool in . NET Core that allows us to modify incoming requests and outgoing responses. It can be used to perform a wide range of tasks such as 
  authentication, logging, compression, and caching. 

 **Types of meddleware in .Net core**
 ### 1. Terminal:- 
   - The terminal middleware is responsible for sending the response back to the client. It is the final middleware component in the pipeline. Terminal middleware can be 
      used to modify the outgoing response before it is sent back to the client.
  **Some examples of terminal middleware include:**
   - Static files middleware: This middleware is used to serve static files such as CSS, JavaScript, and images.
   - File server middleware: This middleware is used to serve files from a specified directory.
   - MVC middleware: This middleware is used to handle requests for MVC endpoints.
 ### 2. Non-Terminal:- 
   - Non-terminal middleware is any middleware component that is not the final component in the pipeline. Non-terminal middleware can be used to modify incoming requests 
    and outgoing responses.
  **Some examples of non-terminal middleware include:**
   - Authentication middleware: This middleware is used to authenticate users.
   - Authorization middleware: This middleware is used to authorize users to access certain resources.
   - Response compression middleware: This middleware is used to compress the response before it is sent back to the client.
   - Request logging middleware: This middleware is used to log requests.
   - Routing middleware: This middleware is used to route requests to the appropriate endpoint.
## How to Pass Data from Controller to View in MVC.
  - In ASP.NET Core MVC, you can pass data from a controller to a view using several methods. Here’s a brief overview of the most common techniques:
    ### 1. ViewData
    ### 2. ViewBag
    ### 3. Strongly Typed Models
    
## Access Modifier
  **1. public:** The member is accessible from any code in the same assembly or another assembly that references it.
  
  **2. private:** The member is accessible only within the containing class or struct.
  
  **3. internal:** The member is accessible only within the same assembly.
  
  **4. protected:** The member is accessible within its containing class and by derived classes.
  
  **5. protected internal:**  The member is accessible within the same assembly and from derived classes, even if they are in another assembly.
  
  **6. private protected:** The member is accessible only within the containing class and derived classes in the same assembly.
  
## types of Class 
 - In C#, class is a group of similar objects. It is a template from which objects are created. It can have fields, methods, constructors etc.
   **Types of Class:-**
    ### 1. Standard Class
      - A standard class in C# is the most common type of class used to define objects. It can contain fields, properties, methods, and events.
    ### 2. Static Class
      - A static class is a class that cannot be instantiated. All members of a static class must also be static. It is commonly used to hold utility methods.
    ### 3. Abstract Class
      - An abstract class is a class that cannot be instantiated and is designed to be subclassed. It can contain abstract methods (without implementation) and concrete 
        methods (with implementation).
    ### 4. Sealed Class
      - A sealed class is a class that cannot be inherited. It is used to prevent other classes from deriving from it.
    ### 5. Partial Class
      - A partial class allows its definition to be split across multiple files. All parts are combined into a single class when the application is compiled.
    ### 6. Nested Class
      - A nested class is a class defined within another class. It is used to logically group classes that are only used within the containing class.
     
## Heap and Stack Memory.
  **Heap:-**
   - The heap is a region of memory used for dynamic memory allocation. It stores reference types and objects that can grow or shrink in size during the program's execution.
     
  **Stack:-**
  - The stack is a region of memory that stores value types and the execution context of methods (including local variables and method parameters). It operates on a last- 
    in, first-out (LIFO) basis.
## Advantage and disadvantage of microservice in Asp .Net core
  **Advantage:-**
   #### 1. Microservices can be scaled independently. If a particular service requires more resources, it can be scaled without affecting the entire system.
   #### 2. Different microservices can use different technologies and frameworks best suited for their tasks.
   #### 3. If a microservice fails, it doesn’t necessarily bring down the entire system.
   #### 4. Teams can develop, test, and deploy microservices independently.
  **Disadvantage:-**
   #### 1. Managing multiple microservices can be complex, requiring sophisticated orchestration and monitoring tools.
   #### 2. Inter-service communication over the network can introduce latency.
   #### 3. Maintaining data consistency and integrity across microservices can be challenging.
   #### 4. Deploying and managing multiple services can be resource-intensive and require advanced CI/CD pipelines.
## linq in details 
 - In ASP.NET Core, LINQ is commonly used to query databases, especially with Entity Framework Core, a popular object- 
    relational mapping (ORM) framework. EF Core allows developers to interact with databases using C# objects, and LINQ 
    provides a natural and efficient way to query and transform this data.
   
## Types of APIs
  **There are several types of APIs, each serving different purposes and operating in various ways. Here are some of the most common types:**

### 1. REST API (Representational State Transfer)
- *Principles*: Uses HTTP requests to perform CRUD operations (Create, Read, Update, Delete).
- *Methods*: GET, POST, PUT, DELETE, PATCH.
- *Characteristics*: Stateless, cacheable, uniform interface, client-server architecture.
- *Use Case*: Web services, where scalability and simplicity are key.

### 2. SOAP API (Simple Object Access Protocol)
- *Principles*: Uses XML-based messaging protocol for exchanging information.
- *Characteristics*: Strict standards, supports ACID compliance, built-in error handling.
- *Use Case*: Enterprise-level applications requiring high security and complex transactions.

### 3. GraphQL API
- *Principles*: Developed by Facebook, allows clients to request only the data they need.
- *Characteristics*: Single endpoint, flexible queries, strong typing, real-time updates.
- *Use Case*: Applications needing complex queries and real-time data fetching.

### 4. gRPC (Google Remote Procedure Call)
- *Principles*: Uses HTTP/2 for transport, Protocol Buffers (Protobuf) for serialization.
- *Characteristics*: High performance, supports multiple languages, bi-directional streaming.
- *Use Case*: Microservices architecture where low latency and high throughput are essential.

### 5. XML-RPC
- *Principles*: Uses XML to encode its calls and HTTP as a transport mechanism.
- *Characteristics*: Simplicity, good for lightweight data structures.
- *Use Case*: Legacy systems and applications that still rely on XML.

### 6. JSON-RPC
- *Principles*: Similar to XML-RPC but uses JSON format.
- *Characteristics*: Lightweight, simple to implement.
- *Use Case*: Simple remote procedure call protocols needing minimal setup.

### 7. WebSockets
- *Principles*: Allows for full-duplex communication channels over a single TCP connection.
- *Characteristics*: Real-time, persistent connection, low latency.
- *Use Case*: Real-time applications like chat applications, live updates, and online gaming.

### 8. OpenAPI (formerly Swagger)
- *Principles*: Specification for building and documenting RESTful APIs.
- *Characteristics*: Standardized, supports auto-generation of documentation, interactive API explorers.
- *Use Case*: Creating, documenting, and consuming REST APIs.

### Comparison and Use Cases
- *REST vs SOAP*: REST is more flexible and easier to use with web applications, while SOAP is better for enterprise applications requiring high security and transaction management.
- *GraphQL vs REST*: GraphQL offers more flexibility and efficiency for complex queries, whereas REST is simpler and more widely used.
- *gRPC vs REST*: gRPC provides higher performance and is suitable for microservices, whereas REST is more broadly adopted and easier to implement.

Choosing the right type of API depends on the specific needs of your application, such as the complexity of data interactions, performance requirements, and ease of implementation.
## Authentication 
  - Authentication is the process of verifying the identity of a user or system. It ensures that the entity trying to access the application is who they claim to be. Common 
   methods include.
 - Username and Password: The most basic form, where users provide a username and password to log in.
 -  Multi-Factor Authentication (MFA): Adds an extra layer of security by requiring additional verification methods (e.g., SMS codes, authentication apps).
 -  OAuth: Allows users to log in using credentials from another service (e.g., Google, Facebook).
 -  Biometric Authentication: Uses fingerprints, facial recognition, or other biometric data.
## Authorization
 - Authorization determines what actions and resources an authenticated user can access. It involves assigning roles and permissions to users. Common approaches include.
 - Attribute-Based Access Control (ABAC): Access is granted based on attributes (e.g., user department, time of access).
 - Access Control Lists (ACLs): Lists that specify which users or system processes are granted access to objects
## Web API and Web API 2.0 Difference
  - Web API: Relied heavily on conventional routing, often leading to less readable and maintainable routes.
  - Web API 2.0: Introduced attribute routing, allowing you to define routes directly on controller actions, making URLs more expressive and easier to manage.
## Diff between Abstract class and interface
## Inheritance
## Polymorphism
## Abstraction 
## Encapsulation
## Understanding SDLC
## transactions
## Fundamental Concepts
## Middleware and Routing
## Entity Framework Core
## Authentication and Authorization
## Performance and Optimization
## Configuration and Environment
## Deployment and Hosting
## Entity Framwork Core and ADO .Net and Dapper ***
## how to design database schema in ms sql server

     
  

 
