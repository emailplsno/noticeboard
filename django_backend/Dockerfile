# Use an official Python 3.11 runtime as a parent image
FROM python:3.11-slim

# Create a non-root user
RUN groupadd -r containeruser && useradd -r -g containeruser nonrootuser

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy and install any needed packages specified in requirements.txt and update everything
COPY requirements.txt ./
RUN apt-get update && apt-get install -y build-essential \
  && pip install --no-cache-dir -r requirements.txt \
  && apt-get remove -y build-essential && apt-get autoremove -y && apt-get clean

# Copy the rest of the application code
COPY . .

# Set ownership and switch to non-root user
RUN chown -R containeruser:nonrootuser /usr/src/app
USER nonrootuser

# Make port 8000 available to the world outside this container
EXPOSE 8000

# Run the app
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
