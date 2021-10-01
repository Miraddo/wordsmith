## Build stage 
FROM maven:3-jdk-8-alpine AS builder
WORKDIR /build
COPY pom.xml .
COPY src src
RUN mvn verify

## Package Image
FROM openjdk:8-jre-alpine 
WORKDIR /app
COPY --from=builder /build/target/ /app
CMD ["java", "-Xmx8m", "-Xms8m", "-jar", "./words.jar"]




