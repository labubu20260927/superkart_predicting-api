
# Use an official Python runtime as a parent image
FROM python:3.9-slim-buster

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Make port 7860 available to the world outside this container
EXPOSE 7860

# Run the application using Gunicorn
# Gunicorn is a Python WSGI HTTP Server for UNIX. It's a pre-fork worker model.
# It's more robust and suitable for production than Flask's built-in server.
# --bind 0.0.0.0:7860 tells Gunicorn to bind to all network interfaces on port 7860.
# app:app refers to the 'app' variable inside the 'app.py' file.
CMD exec gunicorn --bind 0.0.0.0:7860 --workers 1 app:app
