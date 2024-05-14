# Stage 1: Build the Go application
# alpine is an operating system
FROM golang:1.22-alpine AS builder

# Set the Current Working Directory inside the container

# create a directory with the name app and cd to that directory
WORKDIR /app


# Copy the source from the current directory to the Working Directory inside the container
COPY . .

# Build the Go app
RUN go build -o main .

# Stage 2: Create a small image with the compiled binary
FROM alpine:latest

# Set the Current Working Directory inside the container
WORKDIR /root/

# Copy the Pre-built binary file from the previous stage
COPY --from=builder /app/main .

# Expose port 8080 to the outside world
EXPOSE 8080

# Command to run the executable
CMD ["./main"]
