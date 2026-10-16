# Use Node.js 18 as the base image
FROM node:18-alpine

# Set the working directory
WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy application files
COPY . .

# Create a directory for the SQLite database
RUN mkdir -p /app/data

# Expose port 5000 for the backend
EXPOSE 5000

# Start the backend server
CMD ["npm", "start"]
