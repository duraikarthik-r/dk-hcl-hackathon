FROM maven:3.9-eclipse-temurin-17 as build
WORKDIR /workspace/app
COPY pom.xml .
COPY src ./src
RUN mvn clean package -DskipTests
FROM eclipse-temurin:17-jre-alpine
WORKDIR /app
COPY --from=build /workspace/app/target/order-service-0.0.1-SNAPSHOT.jar ./order-service.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","/app/order-service.jar"]