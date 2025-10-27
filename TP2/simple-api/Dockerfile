# Build
FROM maven:3.9.9-amazoncorretto-21 AS simple-api-build
ENV SIMPLE_API_HOME=/opt/simple-api
WORKDIR $SIMPLE_API_HOME
COPY pom.xml .
COPY src ./src
RUN mvn package -DskipTests

# Run
FROM amazoncorretto:21
ENV SIMPLE_API_HOME=/opt/simple-api
WORKDIR $SIMPLE_API_HOME
COPY --from=simple-api-build $SIMPLE_API_HOME/target/*.jar $SIMPLE_API_HOME/simpleapi.jar

ENTRYPOINT ["java", "-jar", "simpleapi.jar"]
