# Pull Python image

# FROM python:3.11.6-alpine3.18
FROM python:3.8-alpine

# Set work directory
WORKDIR /app

# Copy requirements file to the image
# COPY requirements.txt requirements.txt
COPY requirements.txt ./

# Install the packages from the file
# RUN pip3 install -r requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copy the code to the container
COPY . .

ENV FLASK_APP=main.py

ENV FLASK_DEBUG=1


EXPOSE 5000

# Start python application
# CMD ["python", "main.py"]

CMD ["flask", "run", "--host", "0.0.0.0"]