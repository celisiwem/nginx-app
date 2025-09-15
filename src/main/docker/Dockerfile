# Stage 1: Build Quarkus app
FROM eclipse-temurin:21 AS build
WORKDIR /app
COPY . .
RUN ./mvnw package -DskipTests

# Stage 2: Run Quarkus app
FROM eclipse-temurin:21-jdk-alpine
WORKDIR /work/
COPY --from=build /app/target/*-runner /work/application
EXPOSE 8080
CMD ["./application", "-Dquarkus.http.host=0.0.0.0"]
