![[Pasted image 20240417191117.png|1200]]
![[Pasted image 20240417204609.png]]

có thể dùng intern() để copy 1 String Object, bỏ vào trong String Pool
Ex:
```java
String a = new String("Hello");
String b = a.intern();
```