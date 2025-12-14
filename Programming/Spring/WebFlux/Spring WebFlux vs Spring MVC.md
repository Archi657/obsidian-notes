#spring #comparison #architecture

| Feature           | Spring MVC                   | WebFlux                                     |
|------------------|------------------------------|---------------------------------------------|
| Programming Model | Imperative                   | Reactive                                    |
| Blocking          | Blocking                     | Non-blocking                                |
| Thread Model      | Thread-per-request           | Event loop                                  |
| Concurrency       | Limited by threads           | High concurrency                            |
| Reactive Library  | —                            | Project Reactor (Mono, Flux)                |
| Best Use Case     | CPU-bound                    | I/O-bound, streaming                        |

## When to use WebFlux
- Thousands of concurrent connections
- Streaming data
- Non-blocking I/O

## When NOT to use WebFlux
- Simple CRUD
- Blocking JDBC
