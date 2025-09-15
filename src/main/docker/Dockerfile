# build the whole application in a single stage
# ./mvnw clean package
# OR
# ./mvnw clean package -DskipTests


# Step 1: Use a lightweight JDK runtime
FROM eclipse-temurin:21-jre AS runtime

# Step 2: Set work directory
WORKDIR /app

# Step 3: Copy the uber-jar into the container
COPY target/*-runner.jar /app/application.jar

# Step 4: Expose the Quarkus default port
EXPOSE 8081

# Step 5: Run the jar
ENTRYPOINT ["java", "-jar", "/app/application.jar"]

# --------------------------------------------------------------------------------------------
# Copy and paste the following commands in your terminal to build and run the Docker image
# --------------------------------------------------------------------------------------------


#Step 6: build and run the image
#mvn clean package -DskipTests

#Step 7: Build the Docker image
# cd into the messaging-queuing-service directory
# Make sure docker daemon is running

# docker build -f src/main/docker/Dockerfile -t messaging-queuing-service:latest .

#Step 8: Run the Docker container
# docker run -i --rm -p 8081:8081 messaging-queuing-service:latest