FROM node:18-alpine AS build
WORKDIR /usr/src/app
COPY application-service/package*.json ./
RUN npm install
COPY application-service/. .
EXPOSE 3001
CMD ["node", "src/index.js"]