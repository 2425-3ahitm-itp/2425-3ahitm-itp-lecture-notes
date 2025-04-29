FROM maven:3.9.9-eclipse-temurin-21 AS builder

ARG MAIN_CLASS=ServerSingleThreaded

COPY src/main/java/at/htl/$MAIN_CLASS.java /usr/local/src/
WORKDIR /usr/local/src/
RUN javac $MAIN_CLASS.java
CMD ["java", "$MAIN_CLASS"]

# Build the image
FROM eclipse-temurin:21
RUN mkdir -p /opt/app
COPY --from=builder /usr/local/src/*.class /opt/app/at/htl/
WORKDIR /opt/app
CMD ["java","at.htl.ServerSingleThreaded"]



