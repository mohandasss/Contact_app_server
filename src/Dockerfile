FROM maven:3.8.5-openjdk-17 AS build
COPY . .
RUN mvn clean package -DskipTests


FROM maven:3.8.4-openjdk-17-slim
COPY --from=build /target/contactapi-main-0.0.1-SNAPSHOT.jar contactapi-main.jar
EXPOSE 8080
ENTRYPOINT["java","-jar","contactapi-main.jar"]