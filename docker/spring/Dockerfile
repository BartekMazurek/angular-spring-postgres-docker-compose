FROM alpine:latest

WORKDIR /app

COPY app_spring/pom.xml ./

RUN apk update && \
    apk add --no-cache openjdk17 && \
    apk add --no-cache maven

COPY app_spring/. ./

RUN mvn clean install

EXPOSE 8080

CMD ["./mvnw", "spring-boot:run"]
