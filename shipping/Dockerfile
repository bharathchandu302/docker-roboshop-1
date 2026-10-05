FROM maven:3.9.11
EXPOSE 8080
WORKDIR /app/server
COPY pom.xml .
COPY src ./src
RUN mvn clean package
RUN mv target/shipping-1.0.jar shipping.jar
ENV CART_ENDPOINT="cart:8080" \
    DB_HOST="mysql" \
    SPRING_DATASOURCE_URL="jdbc:mysql://mysql:3306/cities?useSSL=false&allowPublicKeyRetrieval=true&autoReconnect=true"
CMD ["java","-jar","shipping.jar"]
