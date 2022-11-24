# Muave ML Web Docker-Compose Stack

## Services

- stable-diffusion-webui
- jupyterhub
- authentik

## Setup

1. Clone this repo
2. Download models for stable-diffusion-webui
   1. Follow (currently step 3 of) the [guide to dependencies](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Dependencies#required-dependencies) for the initial `.ckpt`
   2. Place `.ckpt` into `./apps/diffusion-webui/models/Stable-diffusion`
3. Setup `.env`
   1. copy `.env.example` to `.env`
   2. Fill out variables, such as passwords, as needed.
4. `docker-compose build`
5. `docker-compose up -d`
6. To stop: `docker-compose down`
