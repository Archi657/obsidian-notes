Spring MVC is imperative and blocking while WebFlux is reactive and non-blocking.
WebFlux uses Reactor (Project Reactor) and supports reactive streams, MVC relies on the thread-per-request model
WebFlux can handle higher number of concurrent connections due to its event-driven nature

Mono single value (user ID)
Flux multiple values (real-time stock prices)

**Webclient** reactive alternative to RestTemplate for making non-blocking HTTP calls.
```Java
WebClient webClient = WebClient.create("http://localhost:8080");

Mono<String> response = webClient.get()
.uri("/users/1")
.retrieve()
.bodyToMono(String.class);
```

**Handle errors**
onErrorResume() or @ExceptionHandler
```Java
Mono<String> result = someMono.onErrorResume(e -> Mono.just("Fallback"));

@RestControllerAdvice

public class GlobakExceptionHandler{ 
	@ExceptionHandler(UserNotFoundException.class)
	
	public Mono<ResponseEntity<String>> handleUserNotFound(UserNotFoundException ex){
		return Mono.just(ResponseEntity.status(HttpStatus.NOT_FOUND).body(ex,getMessage()));
	}
}
```

**Backpressure**
	Controls data flow between producers and consumers to avoid overwhelming the system.
WebFlux handles backpressure using onBackpressureDrop(), onBackpressureBuffer()
**Future Class in Java**

Asyncronous and Non-blocking
![[Pasted image 20251110212813.png]]
1- subscriber subs to publisher
2- publisher returns subscription
3- subscriber needs data, makes a request
4- onNext(data) as many times required
5- onComplete()
![[Pasted image 20251110214224.png]]
1- Project Reactor
```Java
// Mono class
private Mono<String> textMono(){
	return Mono.just("Java").log();
	//.justOrEmpty() accepts null
}

// Flux class
private Flux<String> textFlux(){
	// List<String> pn = List.of("a","b")
	//Flux.fromIterable / fromArray / fromStream
	
	return Flux.just("a", "b")
}

//Map
private Flux<String> testMap(){ 
	//Flux<String> flux = Flux.just("a","b");
	// return flux.map(s -> s.toUpperCase(Locale.ROOT))
}
//FlatMap
private Flux<String> testMap(){ 
	//Flux<String> flux = Flux.just("a","b");
	// return flux.flatMap(s -> Mono.just(s.topUpper...))
}
//Skip
private Flux<Integer> testMap(){ 
	//Flux<Integer> flux = Flux.range(1,10);
	// return flux.skipLast(2)
	// return flux.skipWhile(n -> n>5)
	// until the condition is meet it will skip
}
//Concat
private Flux<Intenger> testConcat(){
	Flux<Integer> flux_1 = Flux.range(1, 20);
	Flux<Integer> flux_2 = Flux.range(101, 20);
	
	return Flux.concat(flux_1, flux_2);
}
//Merge
private Flux<Integer> testMerge(){
	
	Flux<Integer> flux_1 = Flux.range(1, 20)
		.delayElements(Duraction.ofSeconds(1));
		
	Flux<Integer> flux_2 = Flux.range(101, 20);
	
	return Flux.merge(flux_1, flux_2);
}
//Zip upp to tuble8
private Flux<Tuple2<Integer, Integer>> testZip() { 
	Flux<Integer> flux_1 = Flux.range(1,10);
	Flux<Integer> flux_2 = Flux.range(100,200);
	
	return Flux.zip(flux_1, flux_2);
}
//Collect
	Flux<Integer> flux = Flux.ranger(1,10) ;
	flux.collectList() ;
}
//Buffer
private Flux<List<Integer>> testBuffer(){ 
	Flux<Integer> flux = Flux.range(1,20)
		.delayElements(Duration.ofMillis(1000));
	return flux.buffer(Duration.ofSeconds(3));
}
//map collection
private Most<Map<Integer, Integer>> testBuffer(){ 
	Flux<Integer> flux = Flux.range(1,20);
	return flux.collectMap(integer -> integer, integer -> integer*integer);
}
main {
	Mainclass object = new Mainclass();
	object.textMono().subscribe(data -> sout(data));
	// System.out::println lambda version
}

```
## Do it
```Java
private Flux<Integer> testDoFunctions() { 
	Flux<Integer> flux = Flux.range(1,10);
	return flux.doOnEach(signal -> {
		if(signal.getType() == SignalType.ON_COMPLETE){
			SOUT I am done
		}else{
			sout signal.get()
		}
	});
}
```
### Do on Complete
```Java
private Flux<Integer> testDoFunctions() { 
	Flux<Integer> flux = Flux.range(1,10);
	return flux.doOnComplete(() -> sout I am done);
}
```
### Do On Next
```Java
private Flux<Integer> testDoFunctions() { 
	Flux<Integer> flux = Flux.range(1,10);
	return flux.doOnNext(integer -> sout integer);
}
```
### DoOnSuscribe
```Java
private Flux<Integer> testDoFunctions() { 
	Flux<Integer> flux = Flux.range(1,10);
	return flux.doOnSuscribe(subscription -> sout suscribed subscription);
}
```
### DoOnCancel
```Java
private Flux<Integer> testDoFunctions() { 
	Flux<Integer> flux = Flux.range(1,10)
		.delayElements(Duration.ofSeconds(1));
	return flux.doOnNext(() -> sout integer);
}
//requires
Disposable disposable = tutorial.testDoFunction().subscribe()
// Thread.sleep(3_500)
disposable.dispose()
```