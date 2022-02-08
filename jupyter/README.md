# Jupyter

Documents how to create and launch a containerized Jupyter (notebook/lab) environment.

## conda-method

### Build the dockerfile

```
docker build -t dask-tut:conda -f jupyter/dask-lab/conda-method/Dockerfile .
```

### Spin up the image 

```
docker run -it --rm --platform=linux/amd64 -p 9999:9999 -v "${pwd}":/home/jovyan/work --name "dasker" dask-tut:conda
```

## pip-method

### Build the dockerfile

```
docker build -t dask-tut:pip -f jupyter/dask-lab/pip-method/Dockerfile .
```

### Spin up the image

```
docker run -it --rm --platform=linux/amd64 -p 9999:9999 -v "${pwd}":/home/jovyan/work --name "dasker" dask-tut:pip
```
