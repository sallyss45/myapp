ARG PORT=443
FROM cypress/browser:latest

# Install Python 3 and required packages
RUN apt-get update \
    && apt-get install -y python3 python3-pip \
    && python3 -m pip install --upgrade pip

# Display the Python user base directory
RUN echo $(python3 -m site --user-base)

# Copy requirements.txt and install Python dependencies
COPY requirements.txt /app/requirements.txt
RUN pip install -r /app/requirements.txt

# Copy your application code to the container
COPY . /app/

# Set the working directory
WORKDIR /app

# Set the environment variable for PATH
ENV PATH=/home/root/.local/bin:${PATH}

# Expose the port
EXPOSE $PORT

# Define the command to run the application
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "$PORT"]
