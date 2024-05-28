FROM mcr.microsoft.com/devcontainers/universal:2

RUN dpkg -r --force-depends python3-dev python3-pip python3-setuptools python3-wheel python3.8-dev conda
RUN apt-get update -y 
RUN apt --fix-broken install -y
RUN apt upgrade -y && apt-get install -y postgresql-client unzip -y 
RUN apt-get autoremove -y && apt-get clean -y