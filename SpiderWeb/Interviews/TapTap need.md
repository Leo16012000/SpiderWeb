Java/J2EE
%%Đảo%% 
Java?
%%con, tranh, bao, phân thân thuật%%
OOP? Inheritance -> Abstraction -> Encapsulation -> Polymorphism
%%bao bố, lớp, bảo vệ%%
Encapsulation? Class encapsulate attributes, methods; Access modifiers (control data validation, expose method)
%%thanh tra lợn, máy chạy, dịch giả, biển cảnh báo, hàng ghế trống%%
checked & unchecked exception? 

| Aspect                   | Checked Exceptions                                                          | Unchecked Exceptions                                                                                        |
| ------------------------ | --------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| **Hierarchy**            | Inherits from `Exception` (excluding `RuntimeException`)                    | Inherits from `RuntimeException`                                                                            |
| **Checked by Compiler**  | Yes                                                                         | No                                                                                                          |
| **Declaration Required** | Must be declared in method signature or handled in a try-catch block        | Not required to be declared or handled explicitly                                                           |
| **When to Use**          | For recoverable conditions where the application might handle the exception | For programming errors that could be avoided by better coding practices (e.g., null pointer, out of bounds) |
| **Examples**             | `IOException`, `SQLException`                                               | `NullPointerException`, `ArrayIndexOutOfBoundsException`                                                    |
Lambda expression & Closure? Java không Closure


Microservices
Spring
Hibernate
active in open source community
oop, multi-threading, parallel processing
design patter and data modeling
Spring Boot, Spring Data, Spring Cloud
Tomcat/Jetty
Redis, Kafka, PostgreSQL, MongoDB
monitoring & tracing in distributed system
Networking 
JDBC
Linux OS
