# MicroservicesLab04

Post-Tutorial Questions:
Why is it important to create separate databases for each microservice (e.g., product_service, order_service, inventory_service)?

Keeping separate databases for each microservice is important because it helps maintain data isolation and prevents tight coupling between services. With this, each microservice can change independently without breaking others. It also makes scaling easier and reduces the risk of one service affecting the entire system if something goes wrong.


What role does Flyway play in managing the database schema, and how does it ensure consistency across environments?

Flyway is a migration tool that helps manage database schema changes in a structured and versioned way. Instead of manually updating the database, Flyway applies migration scripts automatically, making sure that every environment stays in sync. This prevents inconsistencies and makes database changes more predictable.


How does Spring Data JPA simplify working with databases in each of the microservices?

Spring Data JPA makes working with databases a lot easier by handling most of the repetitive database code. Instead of writing SQL queries for basic operations, you can just define repository interfaces, and Spring automatically generates the queries itself.


In the InventoryService, why did we use the @Transactional(readOnly = true) annotation, and what is its significance?

This annotation is used to optimize performance for read operations. Since it tells Spring that the method is only reading data and not modifying, the database doesn’t have to worry about locks or transactions, making queries faster and more efficient. It’s especially useful for services that focus on reading.


In a microservices architecture, what are some challenges when ensuring communication between the Product, Order, and Inventory Services?

One of the biggest challenges is making sure that the services can find and talk to each other reliably. Network issues, service failures, and latency can all lead to issues. Another issue is data consistency, since each service has its own database, and there’s no single transaction across all of them.


What are the advantages of using TestContainers for integration testing with MySQL in this lab?

TestContainers makes integration testing easier by running a real MySQL database inside a temporary container, instead of relying on a permanent database that might behave differently. This ensures tests closely match real-world production scenarios. Since the container starts fresh each time, conflicts between tests are avoided. Additionally, it is fully automated, eliminating the need for manual database setup or cleanup.
