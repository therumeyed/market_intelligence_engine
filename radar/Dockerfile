# Spotlight Radar — standalone image. Self-contained on purpose (see README):
# no dependency on the parent project, so it deploys as its own Render service
# with its own URL, independent of the market-intelligence-engine app/DB.
FROM python:3.12-slim

ENV PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1 \
    PIP_NO_CACHE_DIR=1

WORKDIR /app

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .

ENV PORT=8000
EXPOSE 8000

CMD ["sh", "-c", "uvicorn radar_app:app --host 0.0.0.0 --port ${PORT:-8000}"]
