
# MapProxy-Docker

This project is for running a [MapProxy](https://mapproxy.org/) server in a [Docker](https://www.docker.com/) container. It uses [waitress](https://docs.pylonsproject.org/projects/waitress/en/stable/index.html) as a pure-Python WSGI server.
The base map uses OSM map tiles rendered in the OSM "Standard Style".



## Deployment

### Local:
Build the Docker image:

```bash
cd mymapproxy
docker build --no-cache -t mapproxy .
```

Run the Docker container:

```bash
docker run --rm -it --name "mapproxy-test" -p 8080:8080 -v $(pwd)/cache_data:/app/cache_data mapproxy
```
The console should display something like: `INFO:waitress:Serving on http://0.0.0.0:8080`

#### View Demo:

navigate to http://localhost:8080/demo/
 and the MapProxy demo page should be viewable. 

### On our Docker servers:
Start service (also pulls the image from [PCIC's Dockerhub](https://hub.docker.com/r/pcic/mapproxy-docker) if it's not already on a given server):
```bash
docker-compose up -d
```
Stop service:
```bash
docker-compose down
```
#### Docker Demo
https://services.pacificclimate.org/dev/mapproxy/demo

## Releasing

To create a versioned release:

1. Summarize the changes from the last release in `NEWS.md`
2. Commit these changes, then tag the release:

    ```bash
    git add NEWS.md
    git commit -m "Bump to version x.x.x"
    git tag -a -m "x.x.x" x.x.x
    git push --follow-tags
    ```

## License

This service is intended for private and evaluation use only.
The data is licensed under the [Creative Commons Attribution-ShareAlike 2.0 License](http://creativecommons.org/licenses/by-sa/2.0/).

Data extracted from OpenStreetMap after September 2012 is licensed on terms of the [Open Database License, "ODbL" 1.0](http://www.opendatacommons.org/licenses/odbl/), previously it was licensed CC-BY-SA 2.0.

## Acknowledgements

 ### Base Maps

 [OSM](https://www.openstreetmap.org/)

### MapProxy

[MapProxy GitHub](https://github.com/mapproxy)


## Authors

- [@QSparks](https://github.com/QSparks)
- [@eyvorchuk](https://github.com/eyvorchuk)
