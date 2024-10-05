# Stage 1: Build the Python application
FROM python:3.9-slim AS build

# Set the working directory
WORKDIR /app

# Copy requirements.txt and install dependencies
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code
COPY . .

# Stage 2: Runtime
FROM python:3.9-slim

# Set the working directory for the final image
WORKDIR /Frontend/myapp

# Copy installed packages from the build stage
COPY --from=build /usr/local/lib/python3.9/site-packages /usr/local/lib/python3.9/site-packages

# Copy the application code to the runtime image
COPY . .

# Expose the desired port
EXPOSE 5000

# Command to run the application
CMD ["python", "app.py"]  # Change "app.py" to your main application file if needed
