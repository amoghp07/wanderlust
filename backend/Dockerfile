#Stage 1
FROM node:22 AS backend-builder

#Set working directory
WORKDIR /app

#Copy code for backend
COPY . .

RUN npm i

#Stage 2

FROM node:22-slim

#Set Working directory
WORKDIR /app

#Copy code from abobe Stage
COPY --from=backend-builder /app .

COPY .env.sample .env

EXPOSE 5000

CMD ["npm", "start"]
