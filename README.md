This is interconnected project which will show demo for microservices.
First Project - Spring-6-Question-Micro-Service
Second Project - Spring-6-Quiz-Micro-Service
Third Project - Spring-6-Service-Registry
Fourth Project - Spring-6-Api-Gateway-Micro-Service

It will used Spring (6.0.0) and Spring Boot (3.0.0), Postgres DB, Java 17.**
Major Dependencies Used -
Spring-6-Question-Micro-Service - Spring web, Postgres SQL Driver, Spring Data JPA, Lombok, Eureka Discovery Client, OpenFeign.
Spring-6-Quiz-Micro-Service - Spring web, Postgres SQL Driver, Spring Data JPA, Lombok, Eureka Discovery Client, OpenFeign.
Spring-6-Service-Registry - Spring web, Eureka Server.

spring-cloud-starter-gateway is deprecated.
Please use spring-cloud-starter-gateway-server-webflux instead.
Spring-6-Api-Gateway-Micro-Service - spring-cloud-starter-gateway-server-webflux, Eureka Discovery Client.

Spring-6-Question-Micro-Service : This will create a Question Micro Service and will handle all the question rest api's.
Spring-6-Quiz-Micro-Service : This will create a Quiz Micro Service and will handle all the quiz rest api's.
Spring-6-Service-Registry - It will register all the micro services and acts as a server for them.
Spring-6-Api-Gateway-Micro-Service - Common Gateway to call all micro service (through single URL)

Steps to Run.
1. Create 1 microservice e.g. Question Micro Service
2. Create Service Registry as a server and then register 1st microservice i.e. Question Micro Service.
3. Now, the Question Micro Service has been registered and running on server so , it can be called from any other service who has been registered.
4. Now, Create 2nd microservice e.g. Quiz Micro Service , now register it with server i.e. Service Registry.
5. Now, call the 1st microservice from the second microservice i.e. Calling Question Micro Service from the Quiz Micro Service.

a. Run the Server First.
b. Run the first Micro Service.
c. Run the Second Micro Service which is calling first microservice.
d. Then test the apis.
e. Run the api gateway
If your Gateway is working, you should be able to hit routes like:
http://localhost:8765/{service-name}/{endpoint}
Example:
If your quiz microservice is registered in Eureka as QUIZ-SERVICE, then you can access:
http://localhost:8765/question-service/generateQuestions?category=dotnet&numOfQues=3