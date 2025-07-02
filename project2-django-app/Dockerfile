FROM project1-base:latest

# Install Rust and cargo for uv support
RUN apk add --no-cache rust cargo

# Install uv package manager
RUN python3 -m pip install --no-cache-dir uv

# Set working directory (adjust if your app is in a subfolder)
WORKDIR /app

# Copy Django project files (adjust source path if needed)
COPY . .

# Expose Django's default port
EXPOSE 8000

# Run Django dev server using uv
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
