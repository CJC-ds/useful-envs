FROM --platform=linux/amd64 jupyter/base-notebook:lab-3.2.9

USER root

COPY jupyter/dask-lab/pip-method/requirements.txt .

RUN apt-get update && \
    apt-get install -y \
        graphviz \
        git && \
    python -m pip install dask["complete"]  && \
    pip3 install -r requirements.txt

USER jovyan

RUN git clone https://github.com/dask/dask-tutorial.git ./dask-tutorial

EXPOSE 9999

CMD ["jupyter" \
    ,"lab" \
    ,"--ip=0.0.0.0" \
    ,"--port=9999" \
    ,"--allow-root"]