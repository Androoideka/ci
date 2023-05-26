FROM tensorflow/tensorflow:1.15.5-gpu
RUN apt-key del 7fa2af80 && apt-key del 3bf863cc \
    && apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/3bf863cc.pub \
    && apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/machine-learning/repos/ubuntu1804/x86_64/7fa2af80.pub
COPY requirements.txt .
RUN pip --disable-pip-version-check --no-cache-dir install -r requirements.txt \
    && rm requirements.txt && rm -rf /tmp/pip-tmp