FROM node:18-alpine

RUN apk add --no-cache libc6-compat

WORKDIR /app

COPY src/frontend/package*.json ./

RUN corepack enable pnpm && pnpm i --production

COPY src/frontend/. .

RUN pnpm build

EXPOSE 3000

CMD ["node", "dist/server.js"]
