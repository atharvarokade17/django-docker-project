# -------- Stage 1: builder --------
FROM python:3.12-alpine AS builder

RUN apk add --no-cache gcc musl-dev libffi-dev openssl-dev
WORKDIR /app
COPY requirements.txt .
RUN python3 -m pip install --upgrade pip && \
    python3 -m pip wheel --no-cache-dir --wheel-dir /wheels -r requirements.txt

# -------- Stage 2: final runtime image --------
FROM python:3.12-alpine AS final

RUN apk add --no-cache libffi openssl
WORKDIR /app
COPY requirements.txt .
COPY --from=builder /wheels /wheels
RUN python3 -m pip install --no-cache-dir /wheels/*

