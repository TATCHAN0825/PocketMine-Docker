FROM ubuntu:1804

ARG PORT

RUN apt update

RUN mkdir /pmmp
WORKDIR /pmmp

RUN wget -q -O - https://get.pmmp.io | bash -s -

RUN useradd -r -d /pocketmine -p "" -u 1000 -m -g pocketmine pocketmine
RUN chown 1000:1000 /plugins /data . -R
RUN chmod o+x /usr/bin/php

USER pocketmine

ENV TERM=xterm

RUN ./start.sh --no-wizard

EXPOSE ${PORT}}/tcp

EXPOSE ${PORT}}/udp

