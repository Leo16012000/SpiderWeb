![[Pasted image 20240317222849.png]]
Một rắc rối khi dùng Spring là việc cấu hình (**config**) dự án quá **phức tạp**. Bạn phải làm đủ thứ việc chỉ để tạo một web HelloWorld:

- Tạo ==Maven== hoặc Gradle project
- Thêm các thư viện cần thiết
- ==Tạo XML== để cấu hình project, cấu hình các bean
- Code và build thành file ==WAR==
- Cấu hình Tomcat server để ==chạy== được ==file WAR== vừa build
Spring khá mạnh mẽ nhưng việc cấu hình nghe thôi cũng mệt rồi. Do đó Spring boot ra đời, với các ưu điểm:

- Auto config: tự động cấu hình thay cho bạn, chỉ cần bắt đầu code và chạy là được
- Xây dựng các bean dựa trên annotation thay vì XML
- Server Tomcat được nhúng ngay trong file JAR build ra, chỉ cần chạy ở bất kì đâu java chạy được
So sánh với Spring, thì Spring Boot bạn chỉ cần:

- Dùng Spring Initializr, nhập các info của project, chọn thư viện rồi down code về
- Mở source code ra và bắt đầu code
- Chạy ngay trong IDE, hoặc ==build thành file JAR== để chạy được ngay, không cần cấu hình server