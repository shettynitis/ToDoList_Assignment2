# Use an official Python image as a base
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /app

# Copy the application code to the container
COPY . /app

# Install specific versions of dependencies
RUN pip install --no-cache-dir -r requirements.txt
RUN pip install prometheus_flask_exporter

# Expose the port the app runs on
EXPOSE 5000

# Define the command to run the application
CMD ["python", "app.py"]
