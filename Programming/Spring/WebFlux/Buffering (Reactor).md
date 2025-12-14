![[Pasted image 20251118132026.png]]

```java

Flux.range(1, 20)

    .delayElements(Duration.ofMillis(300))

    .buffer(Duration.ofSeconds(2))

    .subscribe(System.out::println);

```
