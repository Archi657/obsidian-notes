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