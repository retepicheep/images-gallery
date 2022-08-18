# images-gallery
Full stack application based on React and Python Flask

## Troubleshooting

Starts without chaching

```
docker-compose build --no-cache frontend
```

This will allow you to start a docker container from the image.  You will start at a command prompt (`--entrypoint=ash`) instead of the usual `npm start` from the dockerfile.  Note:  The apine shell or `ash` isn't always going to be on a docker image.  Often it will be `bash` instead of `ash`.

```
docker run --rm -it --entrypoint=ash  -p 3000:3000/tcp images-gallery_frontend:latest
```
