```java

Flux.range(1, 10)

    .skipLast(2); // skips last 2 elements

  

Flux.range(1, 10)

    .skipWhile(n -> n < 5); // skips until n >= 5

```