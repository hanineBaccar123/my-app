FROM node:lts-alpine

WORKDIR /app

# Copier package.json et package-lock.json d'abord
COPY package*.json ./

# Nettoyer le cache npm et réinstaller
RUN rm -rf node_modules package-lock.json
RUN npm install

COPY . .

RUN npm run build

RUN npm install -g serve

EXPOSE 3000

CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0", "--port", "3000"]