FROM tensorflow/tensorflow:latest-gpu
RUN apt-key del 7fa2af80 && apt-key del 3bf863cc \
    && apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/3bf863cc.pub \
    && apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/machine-learning/repos/ubuntu1804/x86_64/7fa2af80.pub \
    && mkdir /usr/local/nvidia \
    && ln -s /usr/local/cuda/lib64 /usr/local/nvidia/lib64 \
    && ln -s /usr/local/cuda/targets/x86_64-linux/lib /usr/local/nvidia/lib \
    && ln -s /usr/local/nvidia/lib/libcublas.so.11 /usr/local/nvidia/lib/libcublas.so.12 \
    && ln -s /usr/local/nvidia/lib/libcublasLt.so.11 /usr/local/nvidia/lib/libcublasLt.so.12
COPY requirements.txt .
RUN pip --disable-pip-version-check --no-cache-dir install -r requirements.txt \
    && rm requirements.txt && rm -rf /tmp/pip-tmp