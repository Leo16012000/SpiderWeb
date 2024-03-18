![[Pasted image 20240313140252.png|700]]
Nhìn có vẻ dài và khó hiểu, nhưng đại loại sẽ gồm các bước sau:

- IoC container tạo bean bằng cách gọi constructor (có thể inject các bean dependency vào đây)
- Gọi các setter method để inject các bean vào bằng setter based injection
- Các method khởi tạo khác được gọi (không cần quan tâm nhiều)
- `@PostConstructor` được gọi
- Init method được gọi