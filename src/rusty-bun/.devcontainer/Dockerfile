FROM mcr.microsoft.com/devcontainers/universal:2

RUN dpkg -r --force-depends python3-dev python3-pip python3-setuptools python3-wheel python3.8-dev conda
RUN apt-get update -y 
RUN apt --fix-broken install -y
RUN apt upgrade -y && apt-get install -y postgresql-client unzip -y 
RUN sh -c \"$(wget -O- https://github.com/deluan/zsh-in-docker/releases/download/v1.2.0/zsh-in-docker.sh)\" -- -p git -p https://github.com/zsh-users/zsh-autosuggestions -p https://github.com/zsh-users/zsh-completions -p https://github.com/zsh-users/zsh-syntax-highlighting -p git-auto-fetch -p rust
RUN cargo install sccache --locked
RUN echo \"export RUSTC_WRAPPER=/usr/local/cargo/bin/sccache\" >> /home/codespace/.bashrc
RUN echo \"export RUSTC_WRAPPER=/usr/local/cargo/bin/sccache\" >> /home/codespace/.zshrc
RUN apt-get autoremove -y && apt-get clean -y