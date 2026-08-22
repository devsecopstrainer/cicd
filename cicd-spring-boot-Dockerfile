FROM eclipse-temurin:21-jre-jammy
WORKDIR /app
COPY target/*.jar /app/myapp.jar
EXPOSE 8080
ENTRYPOINT [ "java", "-jar", "myapp.jar" ]
