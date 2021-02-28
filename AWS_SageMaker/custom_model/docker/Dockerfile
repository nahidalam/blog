# all tf dockers here https://hub.docker.com/r/tensorflow/tensorflow/tags/?page=1&ordering=last_updated
# nothing for 2.3 !!!
FROM tensorflow/tensorflow:2.2.0rc2-gpu-py3-jupyter

COPY requirements.txt /build/

RUN pip install -r /build/requirements.txt

# Install sagemaker-training toolkit to enable SageMaker Python SDK
RUN pip3 install sagemaker-training

# Copies the training code inside the container
COPY train.py /opt/ml/code/train.py

# Defines train.py as script entrypoint
ENV SAGEMAKER_PROGRAM train.py