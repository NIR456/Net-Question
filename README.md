### Understanding Services and Dependency Injection (DI) in ASP.NET Core
In ASP.NET Core, services are components that provide functionality to our application, like logging, configuration, data access, etc. Dependency Injection (DI) is a technique to achieve Inversion of Control (IoC) between classes and their dependencies. DI makes your application more modular, testable, and maintainable.
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


## Unit testing
## data Stracture


 

       

           



