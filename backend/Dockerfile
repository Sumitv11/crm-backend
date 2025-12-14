# ---------- BUILD STAGE ----------
FROM maven:3.9.6-eclipse-temurin-17 AS build
WORKDIR /build

# Copy pom first for dependency caching
COPY pom.xml .
RUN mvn dependency:go-offline

# Copy source code
COPY src ./src

# Build the application
RUN mvn clean package -DskipTests

# ---------- RUNTIME STAGE ----------
FROM eclipse-temurin:17-jre-alpine
WORKDIR /app

# Copy built JAR from build stage
COPY --from=build /build/target/*.jar app.jar

EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
