FROM node:20.20.2-alpine3.22 AS builder
#FROM node:20
WORKDIR /app
COPY package.json .
COPY *.js .
RUN npm install
#ENV MONGO_URL="mongodb://mongodb:27017/catalogue" \
#    MONGO="true"
#CMD ["node", "server.js"]

FROM node:20.20.2-alpine3.22
WORKDIR /app
COPY --from=builder /app /app
EXPOSE 8080
ENV MONGO_URL="mongodb://mongodb:27017/catalogue" \
    MONGO="true"
RUN addgroup -S roboshop && adduser -S -G roboshop roboshop
RUN chown -R roboshop:roboshop /app
USER roboshop
CMD ["node", "server.js"]