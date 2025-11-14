# ⚡ Spring WebFlux vs Spring MVC


| Feature           | Spring MVC                   | WebFlux                                     |
| ----------------- | ---------------------------- | ------------------------------------------- |
| Programming Model | Imperative                   | Reactive                                    |
| Blocking / non    | Blocking                     | Non                                         |
| Thread Model      | Thread-per-request           | Event loop model                            |
| Concurrency       | Limited by thread pool       | Handles many concurrent requests            |
| Reactive Library  |                              | Project React (Mono, Flux)                  |
| Best Use Case     | CPU-bound, synchronous logic | I/O-bound, high concurrency, streaming data |


> 💡 **Example:**  

> For thousands of concurrent connections (like live stock updates or chat systems), WebFlux performs better due to its event-driven, non-blocking model.

  

---
## ☁️ Reactive Types
### **Mono**

Represents **0 or 1** element.


```java

Mono<String> mono = Mono.just("UserID-123");

```

Useful for:

- Single responses (e.g., `findUserById`)

- HTTP endpoints returning one object
---
### **Flux**

Represents **0 to N** elements.

```java

Flux<String> flux = Flux.just("AAPL", "MSFT", "TSLA");

```
Useful for:

- Real-time streams (e.g., stock prices)

- Continuous emissions
---
## 🌐 WebClient — Reactive HTTP Client

Reactive alternative to `RestTemplate` for **non-blocking HTTP calls**.


```java

WebClient webClient = WebClient.create("http://localhost:8080");
  

Mono<String> response = webClient.get()
    .uri("/users/1")
    .retrieve()
    .bodyToMono(String.class);

```  

✅ Use `.bodyToFlux()` for streaming multiple values.  

✅ Integrates smoothly with Reactor operators (`map`, `flatMap`, `onErrorResume`, etc.)


---
## ⚠️ Error Handling

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

  

---
## 💨 Backpressure


> Backpressure = Control over data flow between producer and consumer.  

> Prevents a fast producer from overwhelming a slow subscriber.


**WebFlux Operators**

- `.onBackpressureDrop()` → drops excess items  

- `.onBackpressureBuffer()` → buffers them temporarily  

  

---
## ⏱️ Reactive Stream Lifecycle
  
```text

1️⃣ Subscriber subscribes to Publisher  

2️⃣ Publisher returns Subscription  

3️⃣ Subscriber requests data (request(n))  

4️⃣ Publisher emits data → onNext(data)  

5️⃣ When complete → onComplete()

```

  

---
## 🧩 Project Reactor Essentials


```java

// MONO

private Mono<String> textMono() {

    return Mono.just("Java").log();

    // .justOrEmpty() accepts null

}

// FLUX

private Flux<String> textFlux() {

    return Flux.just("a", "b", "c");

}

```

  

---

## ⚙️ Transformations

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

  

---
## ⏩ Filtering and Skipping

```java

Flux.range(1, 10)

    .skipLast(2); // skips last 2 elements

  

Flux.range(1, 10)

    .skipWhile(n -> n < 5); // skips until n >= 5

```

  

---
## 🔗 Combining Streams

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

---

## 🧮 Collecting

```java

Flux<Integer> flux = Flux.range(1, 5);

  

// Collect to list

flux.collectList(); // → Mono<List<Integer>>

  

// Collect to map

flux.collectMap(i -> i, i -> i * i); // → {1=1, 2=4, 3=9, ...}

```

---
## 📦 Buffering


```java

Flux.range(1, 20)

    .delayElements(Duration.ofMillis(300))

    .buffer(Duration.ofSeconds(2))

    .subscribe(System.out::println);

```

  

---
## 🧠 doOn...() Side Effects

### **doOnEach()**

Executes on every signal.

```java

Flux.range(1, 5)

    .doOnEach(signal -> {

        if (signal.isOnComplete())

            System.out.println("Done!");

        else

            System.out.println("Value: " + signal.get());

    });

```

  

### **doOnComplete()**

Runs when stream finishes.

```java

Flux.range(1, 5)

    .doOnComplete(() -> System.out.println("Stream completed!"));

```

### **doOnNext()**

Runs for each element.

```java

Flux.range(1, 3)

    .doOnNext(i -> System.out.println("Next: " + i));

```

### **doOnSubscribe()**

Triggered when subscribed.

```java

Flux.range(1, 3)

    .doOnSubscribe(sub -> System.out.println("Subscribed!"));

```

### **doOnCancel()**

Runs when subscription is cancelled.

```java

Flux<Integer> flux = Flux.range(1, 10)

    .delayElements(Duration.ofSeconds(1))

    .doOnCancel(() -> System.out.println("Cancelled!"));

  

Disposable disposable = flux.subscribe();

Thread.sleep(3500);

disposable.dispose(); // triggers doOnCancel

```


---

  

✅ **Bonus Example — Combine Everything**

```java

WebClient webClient = WebClient.create("https://api.github.com");

  

Flux<String> repos = webClient.get()

    .uri("/users/octocat/repos")

    .retrieve()

    .bodyToFlux(JsonNode.class)

    .map(node -> node.get("name").asText())

    .doOnNext(name -> System.out.println("Repo: " + name))

    .onErrorResume(e -> Flux.just("Error fetching repos"))

    .doOnComplete(() -> System.out.println("Done fetching repos!"));

```