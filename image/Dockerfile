FROM ubuntu:latest

LABEL version="1.0"
LABEL description="Samba simple container"
LABEL maintainer="fernandodev"

ENV SMB_CONFIG_FILE=/etc/samba/smb.conf

EXPOSE 137/udp 138/udp 139 445

RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install samba -y && touch /var/log/samba/log.smbd
RUN (echo 8 ; echo 1) | apt-get install smbclient -y
RUN apt-get install ruby-full -y && \
    gem install 'thor' && \
    gem install 'awesome_print' && \
    gem install 'inifile'
RUN groupadd samba

COPY sambinha /usr/bin

HEALTHCHECK --interval=60s --timeout=15s \
            CMD smbclient -L \\localhost -U % -m SMB3
