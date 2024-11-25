# GCP Pubsub Sample Lab
> How to use GCP Pubsub message queue with Spring Boot and Spring Cloud 


This project cover how to use a GCP PubSub service with Java + Spring Boot and Spring Cloud. We have simple exemples 
publising/consuming an single String but also we have more complex examples covering how to publish and consume objects 
with serialization and deserialization of objects including java.util.DateLocal propreties!!     

![](header.png)

## Installation

OS X & Linux & Windows:
You can run the application from the command line with Maven. You can also build a single executable JAR file that 
contains all the necessary dependencies, classes, and resources and run that. Building an executable jar so makes it easy to ship, 
version, and deploy the service as an application throughout the development lifecycle, across different environments, and so forth.

With Maven, you can run the application by using
```sh
./mvnw spring-boot:run
```
Alternatively, you can build the JAR file with
```sh
./mvnw clean package
```
and then run the JAR file, as follows:
```sh
 java -jar target/gcp-pubsub-sample-0.0.1-SNAPSHOT.jar
```

## Usage example

**Testing the application**

Now that the application is running, you can test it. I suggest you to use Postmant to send requests to it´s applications.

**Simple message Postman:**
```sh
GET http://localhost:8080/filas/publish/TESTE NOVA MANSAGEM
```
**Simple message curl:**
```sh
curl --location --request GET 'http://localhost:8080/filas/publish/TESTE NOVA MANSAGEM'
```
**Complex Message ( with object serializer) Postman:**
```sh
POST http://localhost:8080/filas/
PAYLOAD:
{
    "nome": "Mestre Yoda",
    "login": "yoda-root",
    "dataNascimento": "1978-03-13"
}
```

##
**Complex Message ( with object serializer) Curl:**
```sh
curl --location --request POST 'http://localhost:8080/filas/' \
--header 'Content-Type: application/json' \
--data-raw '{
    "nome": "Mestre Yoda",
    "login": "yoda-root",
    "dataNascimento": "1978-03-13"
}'
```
