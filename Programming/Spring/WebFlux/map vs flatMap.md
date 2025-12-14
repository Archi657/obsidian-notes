### **map()**

Transforms each emitted item.

```java

Flux.just("a", "b")

    .map(String::toUpperCase); // → A, B

```


---
### **flatMap()**

Flattens asynchronous results.

```java

Flux.just("a", "b")

    .flatMap(s -> Mono.just(s.toUpperCase())); // → A, B

```

  

> 🧠 Use `map()` for synchronous transformations,  

> `flatMap()` for asynchronous or nested Monos.
