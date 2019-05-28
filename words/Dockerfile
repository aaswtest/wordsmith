FROM ubuntu
RUN apt-get update
RUN apt-get install maven openjdk-8-jdk -y
COPY pom.xml .
RUN mvn verify
COPY . .
RUN mvn verify

FROM openjdk:alpine
COPY --from=0 target target
CMD cd target && exec java -Xmx8m -Xms8m -jar words.jar

