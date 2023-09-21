
# MapProxy-Docker

This project is for running a [MapProxy](https://mapproxy.org/) server in  [docker](https://www.docker.com/) container. It uses [waitress](https://docs.pylonsproject.org/projects/waitress/en/stable/index.html) as a pure-Pyhon WSGI server. 


## Deployment

Build the image 

```bash
cd mymapproxy
docker build --no-cache -t mapproxy .
```

```bash
docker run --rm -it --name "mapproxy-test" -p 8080:8080 mapproxy
```

The console should display something like: `INFO:waitress:Serving on http://0.0.0.0:8080`

## View Demo 
navigate to http://localhost:8080/demo/
 and the MapProxy demo page should be viewable. 
## License

[MIT](https://choosealicense.com/licenses/mit/)


## Acknowledgements

### Base Maps
[cartoDB](https://cartodb-basemaps-a.global.ssl.fastly.net/#13/40.7062/-74.0045)

[OSM](https://www.openstreetmap.org/)

### MapProxy

[MapProxy GitHub](https://github.com/mapproxy)


## Authors

- [@QSparks](https://github.com/QSparks)

