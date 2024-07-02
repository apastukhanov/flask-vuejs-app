# Pull official base image
FROM python:3.10-slim

# Install dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    apt-transport-https \
    libssl-dev \
    libffi-dev \
    gcc \
    python3-dev \
    musl-dev \
    build-essential \
    libpq-dev \
    netcat-openbsd \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Set working directory
WORKDIR /app

# Copy requirements file
COPY requirements.txt /app/

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application
COPY . /app

# Expose the port the app runs on (optional, depending on your app)
EXPOSE 5000

# Command to run the app (update this line based on your app entry point)
CMD ["flask", "run", "--host=0.0.0.0", "--reload"]
