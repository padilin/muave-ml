FROM nvcr.io/nvidia/cuda:11.6.2-base-ubuntu20.04

RUN apt update && \
    apt install software-properties-common -y && \
    add-apt-repository ppa:deadsnakes/ppa -y && \
    apt install -y python3.10 python3.10-venv && \
    update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.10 999 && \
    python3 -m ensurepip

RUN sed -i 's/bullseye main/bullseye main contrib non-free/' /etc/apt/sources.list && \
    apt-get -y update && \
    apt install git ffmpeg libsm6 libxext6 libgl1 -y

ENV NVIDIA_DRIVER_CAPABILITIES=all
ENV NVIDIA_VISIBLE_DEVICES=all
ENV COMMANDLINE_ARGS="--port 7865 --listen --share true"

RUN groupadd -r muave && useradd -r -g muave muave
USER muave
WORKDIR /home/muave

RUN git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui.git

EXPOSE 7865
CMD ["/home/muave/stable-diffusion-webui/webui.sh"]
