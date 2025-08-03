# Python base image
FROM python:3.9-slim

# Set working directory
WORKDIR /app

# Copy and install dependencies
COPY pyproject.toml .
RUN pip install hatch
RUN hatch env create

# Copy application code
COPY . .

# Expose port and run the application
EXPOSE 8000
CMD ["hatch", "run", "uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
