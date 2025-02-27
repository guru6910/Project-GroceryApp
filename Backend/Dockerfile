FROM ubuntu:latest

# Set the working directory
WORKDIR /app

# Update and install required packages
RUN apt update && \
    apt install -y npm curl && \
    curl -fsSL https://deb.nodesource.com/setup_16.x | bash - && \
    apt install -y nodejs && \
    npm install -g pm2

# Copy application files to the container
COPY . .

# Install application dependencies
RUN npm install

# Expose the application port (change 3000 to your app's port if needed)
EXPOSE 5000

# Start the application using PM2
CMD ["pm2-runtime", "start", "server.js", "--name", "grocery-backend"]
