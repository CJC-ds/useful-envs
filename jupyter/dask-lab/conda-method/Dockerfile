FROM --platform=linux/amd64 jupyter/base-notebook:lab-3.2.9

USER root

RUN apt-get update && \
    apt-get install -y \
        graphviz \
        git

USER jovyan

RUN git clone https://github.com/dask/dask-tutorial.git ./dask-tutorial
RUN cd dask-tutorial && \
    conda env update -n base -f binder/environment.yml --prune && \
    . binder/postBuild && \
    cd ..
RUN rm dask-tutorial/github_deploy_key_dask_dask_tutorial.enc

CMD ["jupyter" \
    ,"lab" \
    ,"--ip=0.0.0.0" \
    ,"--port=9999" \
    ,"--allow-root"]