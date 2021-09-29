FROM ubuntu
RUN apt-get update
RUN apt-get install maven openjdk-8-jdk -y
WORKDIR /opt/
COPY . .
RUN mvn verify
CMD java -Xmx8m -Xms8m -jar ./target/words.jar




