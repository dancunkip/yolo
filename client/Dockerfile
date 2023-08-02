FROM node:14-alpine
WORKDIR /app
COPY /package*.json ./
RUN npm install
COPY . . 
FROM node:14.15.4-slim
WORKDIR /app
EXPOSE 3000
CMD ["npm", "start", "build"]
