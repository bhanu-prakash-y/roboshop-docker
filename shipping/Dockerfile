FROM node:20.20.2-alpine3.23 AS builder
WORKDIR /app
COPY package.json .
COPY *.js .
RUN npm install

FROM node:20.20.2-alpine3.23
WORKDIR /app
EXPOSE 8080
COPY --from=builder /app /app 
# This env is going to be handled in configmap in k8
# ENV MONGO="true" \
#     MONGO_URL="mongodb://mongodb:27017/catalogue"
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
RUN chown -R roboshop:roboshop /app
USER roboshop
CMD ["server.js"]
ENTRYPOINT ["node"]











# FROM maven:3.9.14
# EXPOSE 8080
# WORKDIR /app
# COPY pom.xml .
# COPY src ./src
# RUN mvn clean package 
# RUN mv target/shipping-1.0.jar shipping.jar 
# ENV CART_ENDPOINT="cart:8080" \
#     DB_HOST="mysql"
# CMD ["java", "-jar", "shipping.jar"]







# FROM maven:3.9.14 AS builder
# WORKDIR /app
# COPY pom.xml .
# COPY src ./src
# RUN mvn clean package && \
#     mv target/shipping-1.0.jar shipping.jar 

# FROM eclipse-temurin:17-jre-alpine
# EXPOSE 8080
# WORKDIR /app
# RUN addgroup -S roboshop && adduser -S roboshop -G roboshop && \
#     chown -R roboshop:roboshop /app
# COPY --from=builder /app/shipping.jar .
# USER roboshop
# ENTRYPOINT ["java", "-jar", "shipping.jar"]

