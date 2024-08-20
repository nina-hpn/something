# Get base image as python 3.11 alpine
FROM --platform=arm64 python:3.11-alpine

# Using poetry to manage dependencies
RUN pip install poetry

# Set working directory
WORKDIR /app

# Copy the poetry.lock and pyproject.toml files
COPY poetry.lock pyproject.toml ./

# Install dependencies
RUN poetry config virtualenvs.create false && poetry install --no-dev

# Copy the rest of the files
COPY . .

# Run the application
CMD ["python", "app.py"]
