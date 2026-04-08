
FROM node:20.20.2-alpine3.22
WORKDIR /app
COPY package.json .
RUN npm install
COPY *.js .
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue"
CMD ["node", "server.js"]






# FROM node:20
# WORKDIR /app
# COPY package.json .
# RUN npm install
# COPY *.js .
# ENV MONGO="true" \
#     MONGO_URL="mongodb://mongodb:27017/catalogue"
# CMD ["node", "server.js"]