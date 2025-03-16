# Use the latest Node.js LTS version as the base image
FROM node:18-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json first (for better caching)
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install

# Dynamically install the exact version of esbuild required by vite
RUN npm install esbuild@$(node -p "require('./node_modules/vite/package.json').dependencies.esbuild")

# Copy the rest of the application files
COPY . .

# Expose the port used by Vite (default: 3000)
EXPOSE 3000

# Set environment variable to fix file watching inside Docker
ENV CHOKIDAR_USEPOLLING=true

# Start the frontend app in development mode
CMD ["npm", "run", "dev", "--", "--host"]
