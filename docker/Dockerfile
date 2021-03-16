FROM nvidia/cuda:11.0-cudnn8-devel-ubuntu18.04

RUN apt-get update
RUN apt install -y --no-install-recommends \
        wget unzip curl git python3-dev python3-pip \
        language-pack-ja-base language-pack-ja ibus-mozc golang fuse && \
    update-locale LANG=ja_JP.UTF-8

RUN pip3 install -U pip && pip3 install setuptools && \
    pip3 install torch==1.7.0+cu110 torchvision==0.8.1+cu110 -f https://download.pytorch.org/whl/torch_stable.html && \
    pip3 install minio==6.0.0 pycocotools==2.0.2 mlflow==1.14.0 timm==0.4.5 opencv-python==4.4.0.46 \
                 tensorboard==2.4.0

# link python3.8 to python
RUN ln -snf /usr/bin/python3.8 /usr/bin/python

CMD [ "/bin/bash" ]