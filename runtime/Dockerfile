FROM ubuntu:24.04

ARG ver=2.6.10
WORKDIR /root/

RUN apt update && apt install -y libssl-dev libcap-ng-dev libnl-genl-3-dev    liblz4-dev liblzo2-dev libpam0g-dev

COPY openvpn-${ver} /usr/local/openvpn

RUN ln -s /usr/local/openvpn/sbin/openvpn /usr/bin/openvpn

RUN apt install -y easy-rsa && apt-get -y autoremove && apt-get -y clean && apt-get -y autoclean

