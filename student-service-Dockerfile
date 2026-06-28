FROM eclipse-temurin:21-jre-jammy
ENV server.port=7000
WORKDIR /app
COPY target/*.jar /app/myapp.jar
CMD [ "java", "-jar", "myapp.jar" ]
