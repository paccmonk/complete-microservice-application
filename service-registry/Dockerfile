# Stage 1: Build the application
FROM maven:3.8.7 AS build
WORKDIR /app
COPY pom.xml .
COPY src ./src

# This packages the application to jar files
RUN mvn clean package -DskipTests

# Stage 2: Run the application
FROM adoptopenjdk/openjdk11
WORKDIR /app
COPY --from=build /app/target/service-registry-0.0.1-SNAPSHOT.jar .
EXPOSE 8761
CMD ["java", "-jar", "service-registry-0.0.1-SNAPSHOT.jar"]