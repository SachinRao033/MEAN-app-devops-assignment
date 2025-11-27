# Stage 1: Build Angular app
FROM node:18-alpine AS builder

WORKDIR /app

# Copy package files
COPY package*.json ./
RUN npm ci --silent

# Copy source code
COPY . .

# THIS IS THE ONLY LINE THAT MATTERS — they named the prod config "angular-15-crud"
RUN npm run build -- --configuration=angular-15-crud

# Stage 2: Serve with Nginx
FROM nginx:alpine

# Copy built app from builder stage
# The output folder is dist/angular-15-crud (check your angular.json → "outputPath")
COPY --from=builder /app/dist/angular-15-crud /usr/share/nginx/html

# Copy custom nginx config for Angular routing
COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
