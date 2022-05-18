FROM node:14-alpine AS todobackend
WORKDIR /App
EXPOSE 3001
COPY . .
ADD ./node_modules.tar.gz .
CMD ["npm", "start"]
