FROM project1-base:latest

RUN apk add --no-cache rust cargo

RUN python3 -m pip install --no-cache-dir uv

WORKDIR /app

COPY . .

EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
