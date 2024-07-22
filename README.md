data### Understanding Services and Dependency Injection (DI) in ASP.NET Core
Services:- In ASP.NET Core, services are components that provide functionality to our application, like logging, configuration, data access, etc. 
DI :- Dependency Injection (DI) is a technique to achieve Inversion of Control (IoC) between classes and their dependencies. DI makes your application more modular, testable, and maintainable.
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
  --The Repository pattern is a design pattern that isolates data access logic from the business logic. It provides a way to manage data access so that the underlying data 
    source can be changed without impacting the business logic.
    **In ASP.NET Core, there are several types of repositories that you can implement depending on your needs and the complexity of your application. Here are some common 
   types:**
      1. Generic Repository
      2. Specific Repository
     3. Unit of Work with Repository

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
 - Extension methods in C# allow you to add new methods to existing types without modifying their source code. They are a powerful feature that enhances the flexibility and 
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

## How to Pass Data from Controller to View in MVC.
## Heap and Stack Memory.
## Inheritance
## Polymorphism
## Abstraction
## Interface
## Encapsulation
## types of Class
## Access Modifier
## Diff between Abstract class and interface
## linq in details 
## Routing in .Net Core
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
  

 
