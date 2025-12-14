```Java
Mono.fromCallable(() -> blockingOperation())  
.subscribeOn(Schedulers.boundedElastic());

```
