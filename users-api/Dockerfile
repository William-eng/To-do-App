# Base image for building the Spring Boot application
FROM maven:3.6.3-jdk-8-slim AS build

WORKDIR /app
COPY pom.xml .
COPY src ./src
RUN mvn clean install

# Base image for running the application
FROM openjdk:8-jre-slim-buster
WORKDIR /app
COPY --from=build /app/target/users-api-0.0.1-SNAPSHOT.jar app.jar

EXPOSE 8083
ENTRYPOINT ["java", "-jar", "app.jar"]
