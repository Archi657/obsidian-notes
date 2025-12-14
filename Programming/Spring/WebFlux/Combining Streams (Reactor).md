### **concat()**

Sequential — waits for the first Flux to complete.


```java

Flux.concat(Flux.range(1, 3), Flux.range(10, 3));

```

  

---
### **merge()**

Parallel — interleaves emissions.


```java

Flux.merge(

    Flux.range(1, 3).delayElements(Duration.ofMillis(500)),

    Flux.range(10, 3)

);

```
### **zip()**

Combines element-wise into Tuples.

```java

Flux.zip(

    Flux.range(1, 3),

    Flux.range(100, 103)

); // → (1,100), (2,101), (3,102)

```
