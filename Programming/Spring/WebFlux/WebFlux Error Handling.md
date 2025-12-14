### **Inline with Reactor**


```java

Mono<String> result = someMono

    .onErrorResume(e -> Mono.just("Fallback value"));

```

---

### **Global Exception Handling**

```java

@RestControllerAdvice

public class GlobalExceptionHandler {

    @ExceptionHandler(UserNotFoundException.class)
    public Mono<ResponseEntity<String>> handleUserNotFound(UserNotFoundException ex) {
    
        return Mono.just(

            ResponseEntity.status(HttpStatus.NOT_FOUND)

                          .body(ex.getMessage())

        );
    }
}
```

### **Inline with Reactor**
  
```Java
.findAll().map(AppUtils::DBToEntity)
switchIfEmpty(Flux.empty())
```
