# Use a secure and official Java 17 runtime as a parent image
FROM eclipse-temurin:17-jdk-jammy

# Set the working directory inside the container
WORKDIR /app

# Copy the executable JAR file into the container at /app
COPY target/ems-backend-0.0.1-SNAPSHOT.jar app.jar

# Expose port 8080 to the outside world
EXPOSE 8080

# Command to run the application when the container launches
ENTRYPOINT ["java", "-jar", "app.jar"]