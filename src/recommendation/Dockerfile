FROM python:3.12-slim-bookworm AS base

WORKDIR /usr/src/app

COPY requirements.txt ./


RUN pip install --upgrade pip setuptools wheel
RUN pip install -r requirements.txt
RUN pip install setuptools==69.5.1

COPY . .

RUN python -m opentelemetry.instrumentation.bootstrap -a install

ENV RECOMMENDATION_PORT=1010

ENTRYPOINT ["python", "recommendation_server.py"]
