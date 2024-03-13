[[@Primary]]
```
@Component
@Primary
public class VNEngine implements Engine {
    ...
}
```
[[@Qualifier("VNEngine")]]
```
@Component
public class Car {
    @Autowired
    @Qualifier("VNEngine")  // Phải khớp hoa thường luôn nhe
    private final Engine engine;
}

```
[[Life Cycle ???]]

[[Bean Annotation]]
[[5 Scope]]