[[loose coupling]]
DI violated code
```
class ChinaEngine {
    ...
}

class Car {
    private ChinaEngine engine;
    public Car() {
        // Khi tạo Car thì nhớ gắn engine vào :D
        engine = new ChinaEngine();
    }
}

```
Fix: 
```
// Interface đại diện cho mọi loại động cơ
interface Engine {
    ...
}

// ChinaEngine là một loại Engine
class ChinaEngine implements Engine {
    ...
}

// Trong Car thì chỉ dùng Engine (chung chung), không có cụ thể loại nào
// Loại engine cụ thể sẽ được inject vào lúc tạo (không phải gán cứng trong code)
// Do đó có thể tạo Car với các loại Engine khác nhau
class Car {
    // Loại engine nào đó, lợi dụng tính đa hình OOP
    private Engine engine;
    
    // Khi tạo Car thì tạo Engine object trước, rồi inject vào constructor này
    public Car(Engine engine) {
        this.engine = engine;
    }
}

```
[[3 types]]