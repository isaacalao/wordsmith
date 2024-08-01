# WORDS

FROM maven:3-eclipse-temurin-8-alpine

WORKDIR /words

COPY src /words/src

COPY pom.xml /words/

RUN mvn verify 

WORKDIR /words/target

FROM maven:3-eclipse-temurin-8-alpine

COPY --from=0 /words/target .

CMD [ "java", "-Xmx8m", "-Xms8m", "-jar", "words.jar" ]
