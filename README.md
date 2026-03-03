# CTSE Lab 05 — Microservices

Four Spring Boot services wired through a Spring Cloud Gateway.

| Service | Port |
|---|---|
| API Gateway | 8080 |
| Item Service | 8081 |
| Order Service | 8082 |
| Payment Service | 8083 |

## Run

```bash
# Build JARs
(cd item_service && ./mvnw package -DskipTests)
(cd order_service && ./mvnw package -DskipTests)
(cd payment_service && ./mvnw package -DskipTests)
(cd api_gateway && ./mvnw package -DskipTests)

# Start
docker-compose up --build
```

## Endpoints (via Gateway)

| Method | Path | Description |
|---|---|---|
| GET | /items | List all items |
| POST | /items | Add item (plain text body) |
| GET | /items/{id} | Get item by index |
| GET | /orders | List all orders |
| POST | /orders | Place an order |
| GET | /orders/{id} | Get order by ID |
| GET | /payments | List all payments |
| POST | /payments/process | Process a payment |
| GET | /payments/{id} | Get payment by ID |

Import `microservices-lab.postman_collection.json` into Postman to test all endpoints.
