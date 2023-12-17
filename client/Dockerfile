# Build stage
FROM node:14-alpine3.12 AS build
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY . .
#RUN npm run build

# Final stage
FROM node:14-alpine3.12
WORKDIR /usr/src/app
COPY --from=build /usr/src/app ./
EXPOSE 3000
CMD ["npm", "run", "start"]
