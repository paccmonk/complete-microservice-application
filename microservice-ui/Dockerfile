FROM node:12-alpine

WORKDIR /app
COPY package*.json ./
RUN npm install -g @angular/cli@8.3.19 && npm install
COPY . .

EXPOSE 3000
CMD ["ng", "serve", "--host", "0.0.0.0", "--port", "3000"]