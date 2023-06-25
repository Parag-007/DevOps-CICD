# Use an official Golang runtime as the base image
FROM golang:1.19

# Set the working directory in the container
WORKDIR /app

# Copy the Go module files and download dependencies
COPY go.mod go.sum ./
RUN go get ./...

# Copy the rest of the source code
COPY . .

# Set the environment variables for PostgreSQL
ENV DB_HOST=172.31.94.156
ENV DB_USER=postgresql
ENV DB_PASSWORD=1234 
ENV DB_NAME=postgres 
ENV DB_PORT=5432

# Build the Go binary
RUN go build -o main .

# Expose the port on which your API will run
EXPOSE 8080

# Set the command to run the Go binary
CMD ["./main"]
