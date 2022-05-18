FROM node:14-alpine AS todofrontend
WORKDIR /app
EXPOSE 3000
COPY . .
ADD ./node_modules.tar.gz /app
CMD ["npm", "start"] 
