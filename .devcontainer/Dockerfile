FROM python:3.12-slim

# Установка системных зависимостей
RUN apt-get update && apt-get install -y \
    make git openssh-client \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /workspace

COPY requirements.txt /tmp/pip-tmp/
RUN pip install --no-cache-dir -r /tmp/pip-tmp/requirements.txt
