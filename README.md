# Workshop Slides

## Usage Instructions

1. Use docker to serve the content.
```shell
docker run --name codemash --rm -v $PWD/:/usr/share/nginx/html:ro -d -p 8088:80 nginx
``` 

2. Open browser to http://localhost:8088
   <br><br>

3. When you are done, stop the docker container.
```shell
docker stop codemash
```
