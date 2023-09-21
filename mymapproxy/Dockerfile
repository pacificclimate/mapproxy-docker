FROM python:3.10

WORKDIR /app

COPY . . 


RUN apt-get update && apt-get install -y
RUN apt-get install -y python3-pil python3-yaml  
RUN apt-get install -y libgeos-dev libgdal-dev  

RUN apt-get install -y python3-dev libjpeg-dev zlib1g-dev libfreetype6-dev
RUN pip install --upgrade pip
RUN pip install Pillow Shapely PyYAML MapProxy uwsgi requests geojson pyproj

RUN apt-get install -y apache2
RUN apt-get install -y apache2-dev
RUN pip install mod-wsgi
RUN pip install waitress

EXPOSE 8080

RUN chmod +x /app/run.sh


CMD [ "python3","-m","waitress", "--listen", "0.0.0.0:8080", "config:application" ]

