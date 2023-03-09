# Vue website

## Version
vue 3.2.45
node v18.13.0
npm 8.19.3

## Docker
### Build docker image
> docker build -t vue .

### Run docker container
> docker run -p 8080:8080 vue

### Login to docker registry
<strong>Important</strong>: Saved environment variable $CR_PAT is needed.

https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry

> echo $CR_PAT | docker login ghcr.io -u USERNAME --password-stdin

### Tag docker image
> docker tag vue ghcr.io/denzelhopkins/vue:latest

### Push docker image
> docker push ghcr.io/denzelhopkins/vue:latest