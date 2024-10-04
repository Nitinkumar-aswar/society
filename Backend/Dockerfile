# Backend Dockerfile

# Use a Python base image
FROM python:3.9

# Set the working directory
WORKDIR /app

# Copy requirements.txt first to leverage caching
COPY backend/requirements.txt ./

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code
COPY backend/ .

# Expose the port your app runs on
EXPOSE 5000

# Command to run the application
CMD ["python", "app.py"]

