# Use the official Python image
FROM python:3.9-slim

# Set the working directory
WORKDIR /app

# Switch to the root user to install packages
USER root

# Update package lists and install any necessary packages
RUN sudo -s apt-get update && \
    sudo -s apt-get install -y <necessary-packages> && \  # Replace with actual packages if needed
   sudo -s apt-get install -y python3 && \  # Ensure Python 3 is installed
    sudo -s apt-get clean && rm -rf /var/lib/apt/lists/*

# Copy the requirements file
COPY requirements.txt .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code
COPY . .

# Expose the application port
EXPOSE 5000

# Command to run the application
CMD ["python", "app.py"]  # Adjust "app.py" to your main application file
