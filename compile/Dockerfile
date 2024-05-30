FROM ubuntu:24.04

ARG ver=2.6.6
WORKDIR /root/

RUN apt update && apt install -y pkg-config gcc make wget \
   libssl-dev libcap-ng-dev libnl-genl-3-dev \
   liblz4-dev liblzo2-dev libpam0g-dev

RUN wget https://github.com/OpenVPN/openvpn/releases/download/v${ver}/openvpn-${ver}.tar.gz \
   && tar -xzvf openvpn-${ver}.tar.gz

RUN cd openvpn-${ver} \
   && ./configure --disable-dependency-tracking --prefix=/usr/local/openvpn \
   && make && make install

RUN ln -s /usr/local/openvpn/sbin/openvpn /usr/bin/openvpn
 

