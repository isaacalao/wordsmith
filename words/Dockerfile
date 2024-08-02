# WORDS

# BUILD STAGE
ARG ALPINEVER="3-eclipse-temurin-8-alpine"

FROM maven:${ALPINEVER} AS mvnbuild

WORKDIR /words

COPY src /words/src

COPY pom.xml /words/

RUN mvn verify 

WORKDIR /words/target

# RUN STAGE
FROM maven:${ALPINEVER} AS runjar 

COPY --from=0 /words/target .

CMD [ "java", "-Xmx8m", "-Xms8m", "-jar", "words.jar" ]
