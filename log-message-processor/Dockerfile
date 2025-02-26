# Use the official Python image from the Alpine branch for a smaller image size
FROM python:3.7.17-alpine3.18



# Set the working directory
WORKDIR /app

# Copy only requirements.txt first to leverage Docker cache
COPY requirements.txt .
RUN apk add gcc musl-dev python3-dev  musl-dev libffi-dev openssl-dev g++ make
RUN pip install --upgrade pip
# RUN pip install thriftpy
RUN pip install cython==0.29.36
# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code
COPY . .



# Specify the command to run the application
CMD ["python", "main.py"]
