FROM python:3.13.18-slim-bookworm

WORKDIR /app

RUN useradd --create-home --uid 10001 appuser

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY app.py .

ARG APP_VERSION=dev
ENV APP_VERSION=${APP_VERSION}

USER appuser

EXPOSE 5000
CMD ["python", "app.py"]
