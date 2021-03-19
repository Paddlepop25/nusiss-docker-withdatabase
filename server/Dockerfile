# add the base image
FROM node:15

# setup the image
# define env variables
# database
ENV DB_HOST='tvdb'
ENV DB_PORT=3306
ENV DB_USER='root'
ENV DB_PASSWORD='changeit'
# app
ENV PORT=3000 APP_ROOT=/app

# change into APP_ROOT directory
WORKDIR ${APP_ROOT}

# copy files from local machine into container
ADD main.js .
ADD package.json .
ADD package-lock.json .
ADD views views

# install dependencies
RUN npm install

# run the image
# expose port
EXPOSE ${PORT}

# run the application
ENTRYPOINT [ "node", "main.js" ]

# reference
# const pool = mysql.createPool({
# 	host: process.env.DB_HOST || 'localhost',
# 	port: parseInt(process.env.DB_PORT) || 3306,
# 	database: 'leisure',
# 	user: process.env.DB_USER,
# 	password: process.env.DB_PASSWORD,
# 	connectionLimit: 4
# })