# Set the base image to the official MySQL image
FROM mysql:latest

# Set environment variables for root password and new user
ENV MYSQL_ROOT_PASSWORD=myrootpassword
ENV MYSQL_USER=myuser
ENV MYSQL_PASSWORD=mypassword
ENV MYSQL_DATABASE=mydatabase

# Create the new database
RUN echo "CREATE DATABASE $MYSQL_DATABASE;" >> /docker-entrypoint-initdb.d/init.sql

# Create the new user and grant privileges
RUN echo "CREATE USER '$MYSQL_USER'@'%' IDENTIFIED BY '$MYSQL_PASSWORD';" >> /docker-entrypoint-initdb.d/init.sql
RUN echo "GRANT ALL PRIVILEGES ON $MYSQL_DATABASE.* TO '$MYSQL_USER'@'%';" >> /docker-entrypoint-initdb.d/init.sql

# Expose port 3306 for MySQL connections
EXPOSE 3306

