FROM mcr.microsoft.com/devcontainers/python:3.11

ENV PYTHONUNBUFFERED 1

RUN apt-get update \
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install -y gdal-bin libgdal-dev g++

COPY setup.py .


RUN curl -LsSf https://astral.sh/uv/install.sh -o install.sh

RUN ls -l install.sh

RUN sh install.sh

RUN [ -f "$HOME/.local/bin/env" ] && . $HOME/.local/bin/env || echo "$HOME/.local/bin/env not found"

RUN uv venv

RUN uv pip install --system -e .[dev]v]

COPY . .
