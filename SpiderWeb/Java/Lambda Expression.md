```java
Runnable task1 = new Runnable(){
    @Override
    public void run(){
        System.out.println("Task #1 is running");
    }
};

Thread thread1 = new Thread(task1);
thread1.start();
```

```java
// Lambda Runnable
Runnable task2 = () -> { System.out.println("Task #2 is running"); };
// start the thread
new Thread(task2).start();
```
