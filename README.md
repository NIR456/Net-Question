### Understanding Services and Dependency Injection (DI) in ASP.NET Core
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
## Repository in asp .Net core
## Extension Method in C#


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
```
##### Example 2
```
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
```


 

       

           



