FROM node:20-alpine

WORKDIR /app

# Copy package files
COPY package*.json ./

# Clean install dependencies
RUN npm install

# Copy the rest of the application files
COPY . .

# Expose the port used by Vite
EXPOSE 3000

# Set environment variables
ENV NODE_ENV=development
ENV VITE_API_URL=http://backend:5000

# Start the frontend app
CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0"]
