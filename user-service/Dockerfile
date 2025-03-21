# Etapa 1: Construcción
FROM maven:3.9.6-eclipse-temurin-21 AS build
WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests

# Etapa 2: Ejecución
FROM openjdk:21
WORKDIR /app
COPY --from=build /app/target/user-service.jar app.jar
EXPOSE 8087
ENTRYPOINT ["java", "-jar", "app.jar"]
