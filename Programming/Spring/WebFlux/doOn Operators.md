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

