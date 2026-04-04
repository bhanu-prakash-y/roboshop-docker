FROM node:20
WORKDIR /app
COPY package.json .
RUN npm install
COPY *.js .
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb/catalogue"
CMD ["node", "server.js"]