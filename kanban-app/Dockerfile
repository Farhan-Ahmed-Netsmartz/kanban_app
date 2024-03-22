FROM maven:3.6.1-jdk-8-slim AS build
RUN mkdir -p /workspace
WORKDIR /workspace
COPY pom.xml /workspace
COPY src /workspace/src
RUN mvn -f pom.xml clean package

FROM openjdk:8-alpine
COPY --from=build /workspace/target/*.jar app.jar
EXPOSE 8080

#My changes ---start
# Set environment variables to specify PostgreSQL connection details
ENV DB_SERVER=kanban-postgres
ENV POSTGRES_DB=kanban
ENV POSTGRES_USER=kanban
ENV POSTGRES_PASSWORD=kanban
#My changes ---stop


ENTRYPOINT ["java","-jar","app.jar"]
