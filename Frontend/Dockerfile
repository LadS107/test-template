# Use an official Node.js runtime as a parent image
FROM node:14

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install the dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .

# Build the application for production
RUN npm run build

# Set the environment variable for the dist directory
ENV DIST_DIR=dist

# Expose the desired port
EXPOSE 3000

# Command to start the application using the dist directory
CMD ["node", "$DIST_DIR/server.js"]
