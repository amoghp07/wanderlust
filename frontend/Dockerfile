#Stage 1

FROM node:22 AS frontend-builder

WORKDIR /app

COPY . .

RUN npm i

#Stage 2

FROM node:22-slim

WORKDIR /app

COPY --from=frontend-builder /app .

COPY .env.sample .env

EXPOSE 5173

CMD ["npm", "run", "dev", "--", "--host"]
