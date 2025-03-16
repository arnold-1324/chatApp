# Use Node.js as the base image
FROM node:18-alpine

# Set the working directory
WORKDIR /app

# Copy only package.json first
COPY package.json ./

# Install dependencies and generate package-lock.json
RUN npm install

# Copy the rest of the application
COPY . .

# Set environment variables
ENV NODE_ENV=Production
ENV JWT_SECRET=1JTfmgipLMgTSDuBc+UEYe2BfViGHt81f/wtn4JJmdY=

# Expose the backend server port
EXPOSE 5000

# Start the backend server
CMD ["npm", "start"]
