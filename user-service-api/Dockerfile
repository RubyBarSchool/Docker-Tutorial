FROM node:16.15.0
WORKDIR /app
ADD package*.json ./
RUN npm install
ADD . .
CMD node index.js