FROM python:3.10-slim

RUN apt-get update && apt-get install -y \
    python3-pil \
    python3-yaml \
    libgeos-dev \
    libgdal-dev \
    python3-dev \
    libjpeg-dev \
    zlib1g-dev \
    libfreetype6-dev

RUN pip install --upgrade pip \
    Pillow \
    PyYAML \
    MapProxy \
    uwsgi \
    requests \
    geojson \
    pyproj \
    waitress

RUN pip install "shapely==1.7.0"

WORKDIR /app

COPY ./src /app

CMD [ "python3","-m","waitress", "--listen", "0.0.0.0:8080", "config:application" ]

