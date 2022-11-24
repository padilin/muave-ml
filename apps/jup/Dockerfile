FROM jupyterhub/jupyterhub

RUN apt-get -y update && \
    apt install git ffmpeg libsm6 libxext6 libgl1 -y

RUN pip install jupyter_client dockerspawner

ENV NVIDIA_DRIVER_CAPABILITIES=all
ENV NVIDIA_VISIBLE_DEVICES=all

RUN groupadd -r muave && useradd -r -g muave muave
USER muave

EXPOSE 8000
EXPOSE 8080
EXPOSE 8081
#CMD ["jupyterhub"]
CMD ["/bin/bash"]
