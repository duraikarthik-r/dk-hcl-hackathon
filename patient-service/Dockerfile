FROM node:18-alpine AS build
WORKDIR /usr/src/app
COPY patient-service/package*.json ./
RUN npm install
COPY patient-service/. .
EXPOSE 3000
CMD ["node", "src/index.js"]