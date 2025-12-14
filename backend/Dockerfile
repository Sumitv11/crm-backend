# Use lightweight Java runtime
FROM eclipse-temurin:17-jre-alpine

# Set working directory
WORKDIR /src

# Copy JAR file
COPY backend/target/*.jar crm-0.0.1-SNAPSHOT.jar

# Expose port (Render uses 8080)
EXPOSE 8090

# Start application
ENTRYPOINT ["java", "-jar", "crm-0.0.1-SNAPSHOT.jar"]
