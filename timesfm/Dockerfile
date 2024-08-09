# FROM pytorch/pytorch:2.1.2-cuda12.1-cudnn8-runtime
FROM python:3.13.0b1-slim
RUN apt-get update
COPY . /workspace
WORKDIR /workspace
# RUN pip install -r /workspace/
RUN conda env create --file=./timesfm/environment.yml
# RUN conda init
RUN source activate tfm_env
# RUN pip install -e ./timesfm
RUN pip install jupyterlab
CMD ["bash", "-c", "source /etc/bash.bashrc && jupyter lab --no-browser --allow-root --ip='0.0.0.0' --port=2608"]
# docker build -t timesfm .
# docker run --gpus all -v .:/workspace -p 8080:2608 --name timesfm-container -it timesfm
