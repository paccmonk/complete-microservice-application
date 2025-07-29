FROM maven:3.8.7 AS build
WORKDIR /app
COPY pom.xml .
COPY src ./src

RUN mvn clean package -DskipTests

FROM adoptopenjdk/openjdk11
WORKDIR /app
COPY --from=build /app/target/api-gateway-0.0.1-SNAPSHOT.jar .
EXPOSE 8000
CMD ["java", "-jar", "api-gateway-0.0.1-SNAPSHOT.jar"]