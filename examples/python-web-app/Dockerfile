# Use a Python base image
FROM python:3.12-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the requirements.txt to the working directory
COPY requirements.txt .

# Install dependencies and create virtual environment
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv && \
    python3 -m venv /opt/venv && \
    /opt/venv/bin/pip install --no-cache-dir -r requirements.txt

# Ensure the virtual environment is used for subsequent commands
ENV PATH="/opt/venv/bin:$PATH"

# Copy the rest of your application files
COPY . .

# Expose the port your app will run on (change 8000 if necessary)
EXPOSE 8000

# Specify the command to run your application
CMD ["python", "app.py"]  # Replace app.py with your main script
