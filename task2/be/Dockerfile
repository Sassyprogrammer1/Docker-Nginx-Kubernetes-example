#Build satge
FROM node:16-alpine as build
WORKDIR /app

COPY package*.json ./
COPY src/ ./src

RUN npm install
RUN npm run build

# Final stage
FROM node:16-alpine
WORKDIR /app

COPY package.json ./
RUN npm install --only=production

COPY --from=build /app/build/ .

CMD ["node","index.js"]