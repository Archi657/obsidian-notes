Represents **0 or 1** element.


```java

Mono<String> mono = Mono.just("UserID-123");

```

Useful for:
- Single responses (e.g., `findUserById`)
- HTTP endpoints returning one object
### Related
[[Flux]] 
[[Reactive Streams Lifecycle]]