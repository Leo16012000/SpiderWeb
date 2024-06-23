Interface chỉ chứa duy nhất 1 abstract method

```java
@FunctionalInterface
interface MyFunctionalInterface{
	void myMethod();
}
```

Tại sao phải làm vậy?
* Đối với JS, có thể trực tiếp truyền hàm vào làm đối số cho một hàm khác.
VD: fucntion calculate(func(a,b)){
		return func(a,b) + func (a,b-1);
	}
calculate(sum(a,b))
* Đối với Java, strict hơn nên không thể làm vậy, do quan trọng cái type trả về và tham số truyền vào
-> Cần phải tạo functional interface
```java
// Định nghĩa khuôn mẫu cho method truyền vô
@FunctionalInterface
interface Calculable {
    double calculate();
}
...
// Có thể gọi được method trong khuôn mẫu
public void printResult(Calculable func) {
    System.out.println("Result: " + func.calculate());
}
...
// Method thực sự truyền vào, được wrap vô trong khuôn mẫu
printResult(new Calculable() {
    @Override
    public double calculate() {
        return 3.14;
    }
})

```