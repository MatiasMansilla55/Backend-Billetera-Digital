# Etapa 1: Construcción
FROM maven:3.9.6-eclipse-temurin-21 AS build
WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests

FROM openjdk:21
WORKDIR /app
COPY --from=build /app/target/accounts-service.jar app.jar
ENTRYPOINT ["java","-jar","app.jar"]
EXPOSE 8084