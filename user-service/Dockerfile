# Etapa 1: Construcción
FROM maven:3.8.6-eclipse-temurin-21-alpine AS build
WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests

FROM openjdk:21
ARG JAR_FILE=target/user-service.jar
COPY --from=build /app/target/user-service.jar app.jar
ENTRYPOINT ["java","-jar","app.jar"]
EXPOSE 8087