# Pull Python image

FROM python:3.11.6-alpine3.18

# Set work directory
WORKDIR /app

# Copy requirements file to the image
COPY requirements.txt requirements.txt

# Install the packages from the file
RUN pip3 install -r requirements.txt

# Copy the code to the container
COPY . .

EXPOSE 5000

# Start python application
CMD ["python", "main.py"]

# # Create application work dir
# WORKDIR /app

# # Copy dependencies
# COPY requirements.txt ./

# # Install application requirements
# RUN pip3 install -r requirements.txt

# # Copy appliication file
# COPY . /app/

# # Setting flask startup file
# ENV FLASK_APP=main.py

# # Setting the flask debug variable
# ENV FLASK_DEBUG=1

# # Executable Command
# CMD ["python3", "-m" , "flask", "run", "--host=0.0.0.0" ]

# # Expose application port
# EXPOSE 5000