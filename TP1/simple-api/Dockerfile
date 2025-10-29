# Build stage
FROM eclipse-temurin:21-jdk-alpine AS simple-api-build
ENV MYAPP_HOME=/opt/simple-api
WORKDIR $MYAPP_HOME

RUN apk add --no-cache maven

COPY pom.xml .
COPY src ./src
RUN mvn package -DskipTests

# Run stage
FROM eclipse-temurin:21-jre-alpine
ENV MYAPP_HOME=/opt/simple-api
WORKDIR $MYAPP_HOME
COPY --from=simple-api-build $MYAPP_HOME/target/*.jar $MYAPP_HOME/simple-api.jar

ENTRYPOINT ["java", "-jar", "simple-api.jar"]
