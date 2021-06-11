FROM pytorch/pytorch:1.1.0-cuda10.0-cudnn7.5-devel


# COPY sources.list /etc/apt
COPY sources.list /etc/apt/

RUN pip config set global.index-url https://mirrors.cloud.tencent.com/pypi/simple

RUN apt-get update && \
    apt-get install -yq vim curl git zsh cmake && \
    curl -sL https://deb.nodesource.com/setup_12.x | bash - && \
    apt-get install -yq nodejs


RUN pip install jupyterlab \
                IPython \
                opencv-python \
                Pillow \
                matplotlib \
                torch==1.7.1 torchvision \
                easydict \
                tensorflow-gpu==1.15.0 \
                scipy==1.2.1


RUN apt-get update && apt-get install -yq g++  zip unzip

RUN git clone https://github.com/davisking/dlib.git && \
    cd dlib && \
    git checkout v19.21 && \
    python3 setup.py install

