# Java/J2EE
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
%%Consider between notify(), notifyAll()%%
Object methods? clone(), equals(), getClass(), hashCode(), **notify()** and **wait()**, toString()
wait() chờ trên 1 thread, đợi thread khác gọi notify()/notifyAll(). 
```java
public class Buffer { 
	private final int capacity; 
	private final Queue<Integer> queue = new LinkedList<>(); 
	public Buffer(int capacity) { this.capacity = capacity; } 
	public synchronized void put(int value) throws InterruptedException {             while (queue.size() == capacity) { 
	        wait(); // Chờ cho đến khi có không gian trong buffer 
	    } 
	    queue.add(value); System.out.println("Produced " + value); 
	    notify(); // Thông báo cho một thread đang chờ 
	} 
	public synchronized int get() throws InterruptedException { 
		while (queue.isEmpty()) { 
			wait(); // Chờ cho đến khi có phần tử trong buffer 
		} 
		int value = queue.poll(); 
		System.out.println("Consumed " + value); 
		notify(); // Thông báo cho một thread đang chờ return value; 
		} 
	}
```
hashCode() trả mã băm 
toString() trả tên class + mã băm (`Example@6d06d69c`)
```java
@Override 
public boolean equals(Object o) { 
	if (this == o) return true; 
	if (o == null || getClass() != o.getClass()) return false; 
	Person person = (Person) o; 
	return age == person.age && name.equals(person.name); 
} 
@Override 
public int hashCode() { 
	int result = name.hashCode(); 
	result = 31 * result + age; 
	return result; 
}
@Override 
public String toString() { return "Person{name='" + name + "', age=" + age + "}"; }
```
JVM, JIT Compiler? 
Java Virtual Machine, chứa JIT Compiler
javac: .java -> .class compile trước khi chạy
JIT Compiler? .class -> binary compile trong khi chạy
Run-time với JVM và JIT compiler: JVM dùng interpreter thực thi bytecode -> phát hiện hot spot -> JIT Compiler compile hot spot từ bytecode sang binary code -> hot spot được lưu trữ
JIT Compiler vs interpreter? Interpreter giúp chạy nhanh hơn vào lúc đầu, phát hiện hot spot, JIT compiler biên dịch và tối ưu hóa (nhiều kỹ thuật khác nhau mà interpreter đơn giản không thực hiện hiệu quả). Nếu compile all source -> memory không tối ưu do mã máy nặng hơn bytecode
Bytecode vs Assembly?

| Đặc điểm         | Bytecode                               | Assembly                          |
| ---------------- | -------------------------------------- | --------------------------------- |
| **Mục đích**     | Thực thi trên máy ảo, độc lập nền tảng | Giao tiếp trực tiếp với phần cứng |
| **Tính độc lập** | Độc lập nền tảng                       | Phụ thuộc nền tảng                |
| **Thực thi**     | Thông dịch hoặc JIT trên máy ảo        | Biên dịch trực tiếp thành mã máy  |
| **Sử dụng bởi**  | Java, Python, .NET                     | x86, ARM, MIPS                    |

is this Bytecode?? text to bytecode??![[Pasted image 20240806224240.png]]
Serialization? Object into binary format, disk/network/other Java running virtual machine



atomic, volatile, synchronized? 
# Microservices
Spring
Hibernate
active in open source community
oop, multi-threading, parallel processing
design pattern and data modeling
Spring Boot, Spring Data, Spring Cloud
Tomcat/Jetty
Redis, Kafka, PostgreSQL, MongoDB
monitoring & tracing in distributed system
Networking 
JDBC
Linux OS
