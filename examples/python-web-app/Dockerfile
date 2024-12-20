FROM ubuntu

# Set working directory
WORKDIR /app

# Install dependencies
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-dev && \
    apt-get install -y libpq-dev

# Copy requirements.txt and install dependencies
COPY requirements.txt /app/
RUN pip3 install -r requirements.txt

# Copy the entire project into the container
COPY . /app/

# Set environment variable for Django settings module (optional but helpful)
ENV DJANGO_SETTINGS_MODULE=myproject.settings

# Expose the port that Django will run on
EXPOSE 8000

# Define the command to run the Django app
ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]
