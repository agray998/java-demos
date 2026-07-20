FROM maven:3.9.16-amazoncorretto-21-debian AS build

WORKDIR qa
COPY . .
RUN javac qa/training/Lab1.java

FROM ubuntu:latest

RUN apt-get update && apt-get install -y openjdk-21-jre
RUN mkdir -p qa/training

COPY --from=build /qa/training/*.class qa/training/

ENTRYPOINT ["java", "qa.training.Lab1"]
