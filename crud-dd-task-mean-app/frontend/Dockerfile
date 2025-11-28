# Stage 1: Build Angular app
FROM node:18-alpine AS builder

WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm ci --silent

# Copy source code
COPY . .

# Build with the correct configuration (production is the valid one)
RUN npm run build -- --configuration production

# Stage 2: Serve with Nginx
FROM nginx:alpine

# Copy built app from builder stage (matches your project's outputPath)
COPY --from=builder /app/dist/angular-15-crud /usr/share/nginx/html

# Copy custom Nginx config for Angular routing
COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
