# Use the official Node.js image
FROM node:21

# Set the working directory inside the container
WORKDIR /app

# Copy only package.json and package-lock.json first to optimize caching
COPY package.json package-lock.json ./

# Install dependencies
RUN npm ci

# Copy the rest of the application files
COPY . .

# Expose the correct port (5001 in your case)
EXPOSE 5001

# Start the server
CMD ["npm", "start"]

