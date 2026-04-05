FROM node:20
WORKDIR /app
COPY package.json .
RUN npm install
COPY *.js .
ENV redis_host="redis" \
    catalogue_host="catalogue" \
    catalogue_port="8080" \
CMD ["node", "server.js"]