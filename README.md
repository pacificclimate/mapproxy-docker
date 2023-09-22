
# MapProxy-Docker

This project is for running a [MapProxy](https://mapproxy.org/) server in a [Docker](https://www.docker.com/) container. It uses [waitress](https://docs.pylonsproject.org/projects/waitress/en/stable/index.html) as a pure-Python WSGI server.
The base map is the CartoDB "positron" or "light_all" style using OSM data.

## Deployment

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

## View Demo

Navigate to [http://localhost:8080/demo/](http://localhost:8080/demo/), and the MapProxy demo page should be viewable.

## License

This service is intended for private and evaluation use only.
The data is licensed under the [Creative Commons Attribution-ShareAlike 2.0 License](http://creativecommons.org/licenses/by-sa/2.0/).

## Acknowledgments

### Base Maps
- [CartoDB](https://cartodb-basemaps-a.global.ssl.fastly.net/#13/40.7062/-74.0045)

### MapProxy
- [MapProxy GitHub](https://github.com/mapproxy)


## Authors

- [@QSparks](https://github.com/QSparks)

