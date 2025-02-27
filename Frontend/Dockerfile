FROM ubuntu:latest

# Set working directory
WORKDIR /app

# Update and install Node.js and npm
RUN apt update && \
    apt install -y npm curl && \
    curl -fsSL https://deb.nodesource.com/setup_16.x | bash - && \
    apt install -y nodejs

# Copy package.json and package-lock.json first (for better caching)
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application files
COPY . .

# Expose the port your application runs on
EXPOSE 3000

# Start the application
CMD ["npm", "start"]
