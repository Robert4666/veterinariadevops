FROM node:18-alpine AS deps

WORKDIR /app

COPY package*.json ./

RUN npm install --omit=dev

FROM node:18-alpine AS runner

WORKDIR /app

ENV NODE_ENV=production

RUN addgroup -S nodejs && adduser -S nodejs -G nodejs

COPY --from=deps /app/node_modules ./node_modules
COPY . .

RUN chown -R nodejs:nodejs /app

USER nodejs

EXPOSE 3001

CMD ["npm", "start"]
