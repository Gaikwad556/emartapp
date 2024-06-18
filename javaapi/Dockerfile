FROM openjdk:11 AS java-build
WORKDIR /usr/src/app/
COPY ./ /usr/src/app/
RUN apt udpate && apt install maven -y
RUN mvn install -DskipTests

FROM openjdk:11
WORKDIR /usr/src/app/
COPY --from=java-build /usr/src/app/target/book-work-0.0.1-SNAPSHOT.jar ./book-work-0.0.1.jar
EXPOSE 9000:9000
ENTRYPOINT ["java","-jar","book-work-0.0.1.jar"]
