# ---------- Build stage ----------
FROM maven:3.9-eclipse-temurin-17 AS build

WORKDIR /app

# Copy pom.xml and download dependencies first (better cache)
COPY pom.xml .
RUN mvn -q -DskipTests dependency:go-offline

# Copy the rest of the source
COPY src ./src

# Build the jar
RUN mvn -q -DskipTests package

# ---------- Runtime stage ----------
FROM eclipse-temurin:17-jre

WORKDIR /app

# Copy the built jar from the build stage
COPY --from=build /app/target/*.jar app.jar

# Expose Spring Boot port
EXPOSE 8082

# Env vars for DB (override via docker-compose if you want)
ENV DB_HOST=host.docker.internal
ENV DB_PORT=3306
ENV DB_USER=root
ENV DB_PASSWORD=puru8975

# Run the app
ENTRYPOINT ["java", "-jar", "app.jar"]
