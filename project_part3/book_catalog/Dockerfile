# Use an official Python runtime as a parent image
FROM python:3.9-slim

# Set the working directory inside the container to /book_catalog
WORKDIR /book_catalog

# Copy requirements.txt to the working directory inside the container
COPY requirements.txt /book_catalog/requirements.txt

# Install the Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the app's code into the container
COPY . /book_catalog

# Expose port 80 for Azure App Service compatibility
EXPOSE 80
ENV DATABASE_URL="postgresql://db_722week7_user:RFKT5BMc0kcVtIXYEzf3t8I30k1JTJDV@dpg-crj81c3v2p9s738rlho0-a.oregon-postgres.render.com/db_722week7"
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "80"]
