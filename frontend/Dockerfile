
# Use Node.js 18 to build the frontend
FROM node:18-alpine

# Set the working directory
WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm install

# Accept build argument
ARG VITE_API_URL
ENV VITE_API_URL=$VITE_API_URL

# Copy application files
COPY . .

# Build the production application
RUN npm run build

# Use nginx to serve the frontend
FROM nginx:alpine

# Copy the built files to nginx
COPY --from=0 /app/dist /usr/share/nginx/html

# Expose port 80 for nginx
EXPOSE 80

# Start nginx
CMD ["nginx", "-g", "daemon off;"]
