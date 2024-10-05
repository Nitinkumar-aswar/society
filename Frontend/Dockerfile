FROM python:3.9-slim

# Switch to root user to install packages
USER root

# Update and install any necessary packages
RUN sudo apt-get update && \
   sudo apt-get install -y sudo python3 python3-pip && \
   sudo apt-get clean && rm -rf /var/lib/apt/lists/*

# Set the working directory for your application
WORKDIR /Frontend/myapp

# Copy requirements.txt and install Python dependencies
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

# Copy the application code
COPY . .

# Expose the application port
EXPOSE 5000

# Command to run the application
CMD ["python", "app.py"]
