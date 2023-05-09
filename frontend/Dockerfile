# Stage 1: Build
FROM node:21-alpine AS builder

# Set working directory
WORKDIR /app

# Copy package files first for efficient caching
COPY package.json package-lock.json ./

# Install dependencies
RUN npm ci

# Ensure Vite has the correct permissions
RUN chmod +x node_modules/.bin/vite

# Copy the rest of the application code
COPY . .

# Optional: Build the project for production (uncomment for production builds)
# RUN npm run build

# Stage 2: Serve
FROM node:21-alpine

# Set working directory
WORKDIR /app

# Copy necessary files and dependencies from the builder stage
COPY --from=builder /app/node_modules ./node_modules
COPY --from=builder /app ./

# Ensure Vite executable permission (again, for safety)
RUN chmod +x node_modules/.bin/vite

# Expose the port for the Vite development server
EXPOSE 5173

# Start the development server
CMD ["npm", "run", "dev", "--", "--host"]

