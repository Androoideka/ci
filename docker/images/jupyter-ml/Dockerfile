FROM tensorflow/tensorflow:1.15.5-gpu
COPY requirements.txt .
RUN pip --disable-pip-version-check --no-cache-dir install -r requirements.txt \
    && rm requirements.txt && rm -rf /tmp/pip-tmp