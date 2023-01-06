# A Default Story

This repository is a template for creating presentations following a structured storyline.
For formatting and serving the content, it uses reveal.js and docker.

To use, create a copy of this repo and add your own content to tell your story.

## Usage Instructions

#### STEP 1: Create your own "story" repository

1. Open [github.com/new](https://github.com/new) and set "Repository template" to _cdcollab/default-story_.
   <br><br>
2. Complete other details as you wish and click "Create repository."

#### STEP 2: Download reveal.js

1. Clone your new repository and `cd` into it.
   <br><br>
2. Use [vendir](https://carvel.dev/vendir/docs/v0.24.0/install) to download reveal.js.
```shell
vendir sync
mv vendir/reveal.js-4.2.1 .
rm -rf vendir
```
> Note: The .gitignore file prevents reveal.js from being pushed to GtHub.
> This means you must run this step every time you clone your repo.

#### STEP 3: Serve the content

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

#### STEP 4: Personalize!

Refer to [https://revealjs.com/markdown](https://revealjs.com/markdown) for information on using Markdown to create content.