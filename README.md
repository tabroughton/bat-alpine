# bat-alpine
a docker file to build an image of bat based on alpine

The image built from this Dockerfile is on dockerhub:  

```
docker pull tabroughton/docker-alpine
```

bat is a syntax highlighting replacement for linux cat developed by Dan Lynn:  https://github.com/sharkdp/bat

There is a Docker image from bat developer currently based on ubuntu (~260MB image) whereas this image is based on Alpine (creates ~30MB image) that you can use to run bat in a container:

Once image is built:
```
alias bat='docker run -it --rm -e BAT_THEME -e BAT_STYLE -e BAT_TABS -v "$(pwd):/myapp" tabroughton/bat-alpine'
```

Now when you run: ```bat myfile``` the output to the terminal is the contents of myfile formatted with syntax highlighting, line numbers, etc.

Before using it would be worth checking https://hub.docker.com/r/danlynn/ to see if the maintainer of bat has created a more recent (more official) alpine based image.
