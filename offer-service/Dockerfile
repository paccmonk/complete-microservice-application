FROM maven:3.8.7 AS build
WORKDIR /app
COPY pom.xml .
COPY src ./src

RUN mvn clean install
RUN mvn clean package -DskipTests

FROM adoptopenjdk/openjdk11
WORKDIR /app
COPY --from=build /app/target/offer-service-0.0.1-SNAPSHOT.jar .
EXPOSE 8081
CMD ["java", "-jar", "offer-service-0.0.1-SNAPSHOT.jar"]