FROM node:21
RUN apt-get update ; apt-get install -y netcat-openbsd

WORKDIR /app

ARG NEXT_PUBLIC_ISSUER_URL
RUN echo "NEXT_PUBLIC_ISSUER_URL: $NEXT_PUBLIC_ISSUER_URL"

COPY package*.json ./

RUN npm install

COPY . .

RUN NEXT_PUBLIC_ISSUER_URL=$NEXT_PUBLIC_ISSUER_URL npm run build

CMD ["npm", "start"]
