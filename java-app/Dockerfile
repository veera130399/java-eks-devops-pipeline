# Use an OpenJDK base image
FROM openjdk:17-jdk-alpine

# Set working directory inside container
WORKDIR /app

# Copy jar file to container
COPY target/*.jar app.jar

# Run the jar file
ENTRYPOINT ["java", "-jar", "app.jar"]
