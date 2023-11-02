FROM registry.opensuse.org/opensuse/toolbox:latest

LABEL maintainer="Hayath"
LABEL version="1.0"
LABEL description="The Rust In Its Full Glory"

ARG USERNAME
ARG UID
ARG PROJECT_PWD

RUN zypper update -y
# Below is optional
RUN useradd -ms /bin/bash $USERNAME -u $UID; exit 0
RUN usermod -a -G sudo $USERNAME; exit 0
RUN usermod -a -G users $USERNAME; exit 0
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers
USER $USERNAME
ENV USER=$USERNAME
ENV PATH=$PATH:/home/$USERNAME/.local/bin/

WORKDIR "$PROJECT_PWD"
# Below is optional
#########################################
# for diesel_cli
#########################################
