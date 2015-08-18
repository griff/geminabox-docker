# Docker image for geminabox

Runs geminabox in a docker image with puma as simple as:
```
docker run -p 4567:4567 griff/geminabox
```

And then you can point your browser at ```http://localhost:4567```

## Volume

The image stores the gems in /var/geminabox which you can persist with either a state container:
```
docker run --name gems-state -v /var/geminabox busybox true
docker run --volumes-from gems-state -p 4567:4567 griff/geminabox
```

Or using a host directory:

```
docker run -v /var/geminabox:/var/geminabox -p 4567:4567 griff/geminabox
```