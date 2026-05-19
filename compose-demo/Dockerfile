# syntax=docker/dockerfile:1

# Builds an image with the Python 3.12 image
FROM python:3.12-alpine

# Sets the working directory to /code
WORKDIR /code

# Sets environment variables used by flask
ENV FLASK_APP=app.py
ENV FLASK_RUN_HOST=0.0.0.0

# Installs gcc and other dependencies
RUN apk add --no-cache gcc musl-dev linux-headers

# Copies requirements.txt
COPY requirements.txt .

# Installs Python dependencies
RUN pip install -r requirements.txt

# Copies current directory into image
COPY . .

EXPOSE 5000

# Default command
CMD ["flask", "run", "--debug"]