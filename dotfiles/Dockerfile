FROM ubuntu:18.04

ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV LC_ALL ja_JP.UTF-8

RUN apt-get update \
    && apt-get install -y locales \
    && locale-gen ja_JP.UTF-8

RUN apt update -y && apt install -y build-essential cmake
RUN apt update -y && apt install -y git curl wget unzip zsh
RUN apt update -y && apt install -y python python-dev python-pip
RUN apt update -y && apt install -y python3 python3-dev python3-pip

RUN useradd -m himkt
USER himkt

WORKDIR /home/himkt
RUN git clone https://github.com/himkt/dotfiles

WORKDIR /home/himkt/dotfiles
RUN make brew
RUN make brew_bundle
