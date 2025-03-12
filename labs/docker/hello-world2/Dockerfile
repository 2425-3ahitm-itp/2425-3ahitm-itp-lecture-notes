FROM eclipse-temurin:21 AS builder

COPY Main.java /usr/local/src/
WORKDIR /usr/local/src/
RUN javac Main.java
CMD ["java","Main"]

# Build the image
FROM eclipse-temurin:21
RUN mkdir -p /opt/app
COPY --from=builder /usr/local/src/*.class /opt/app/
WORKDIR /opt/app/
CMD ["java","Main"]



