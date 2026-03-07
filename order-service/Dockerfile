# Multi-stage Dockerfile for order-service (Spring Boot)

# build stage
FROM maven:3.9-eclipse-temurin-17 as build
WORKDIR /workspace/app

# copy pom and source
COPY pom.xml .
COPY src ./src

# package application (skip tests to speed up build)
RUN mvn clean package -DskipTests

# runtime stage
FROM eclipse-temurin:17-jre-alpine
WORKDIR /app

# copy jar from build stage
COPY --from=build /workspace/app/target/order-service-0.0.1-SNAPSHOT.jar ./order-service.jar

# expose port defined in application (default 8080)
EXPOSE 8080

ENTRYPOINT ["java","-jar","/app/order-service.jar"]
