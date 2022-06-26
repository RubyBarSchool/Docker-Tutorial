

FROM node:16.15.0
WORKDIR /app
COPY ["package.json","package-lock.json*","./"]
COPY  . .
RUN npm install
CMD node index.js