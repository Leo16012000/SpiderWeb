### Without Default Values (Potential for Errors)

Consider a method that processes a message with an optional debug flag. If the debug flag is `true`, it prints additional debug information. A common approach might involve checking if the argument is null or its Boolean value, which could lead to potential errors:

```
public class MessageProcessor {
    public void processMessage(String message, Boolean debug) {
        if (debug != null && debug) {
            System.out.println("Debugging is enabled. Processing message: " + message);
            // Debugging logic here
        } else {
            System.out.println("Processing message: " + message);
            // Standard processing logic here
        }
    }
}

```

