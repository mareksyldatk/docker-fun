# jupyter-python-latest docker image

Building:

```
docker build -t jupyter-python-latest .
```

Running in interactive mode:

```
docker container run --rm -it -p 3000:8888 -v $(pwd)/notebooks:/usr/notebooks jupyter-python-latest
```
where `3000` is port to access via the browser (`localhost:3000`) and `$(pwd)/notebooks` is local folder with notebooks (to use current folder use only `$(pwd)`).

Push to docker hub:

```
docker tag jupyter-python-latest mareksyldatk/jupyter-python-latest
docker push mareksyldatk/jupyter-python-latest
```
