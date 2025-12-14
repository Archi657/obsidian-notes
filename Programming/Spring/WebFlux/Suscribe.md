```Java
WebClient webClient = WebClient.create("http://localhost:8080");
Flux<Factura> facturasFlux = webClient.get()    
    .uri("/facturas").retrieve().bodyToFlux(Factura.class);
facturasFlux.subscribe(factura -> System.out.println(factura));
```