FROM python:3.10-slim

ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1

WORKDIR /app

# Instala dependencias del sistema
RUN apt-get update && apt-get install -y netcat-openbsd gcc libpq-dev


COPY backend/requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY backend .

RUN chmod +x entrypoint.sh

ENTRYPOINT ["/app/entrypoint.sh"]
