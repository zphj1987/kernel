FROM ubuntu:bionic

RUN apt-get update -y && \
    apt-get install -y git-core gnupg flex bison gperf build-essential \
    zip curl zlib1g-dev libc6-dev-i386 \
    lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z-dev ccache \
    libgl1-mesa-dev libxml2-utils xsltproc unzip mtools u-boot-tools \
    htop iotop sysstat iftop pigz bc device-tree-compiler lunzip \
    dosfstools gcc-aarch64-linux-gnu g++-aarch64-linux-gnu \
    gcc-arm-linux-gnueabi g++-arm-linux-gnueabi ccache \
    sudo cpio nano vim kmod kpartx wget bsdtar qemu-user-static \
    pxz ruby-dev debootstrap multistrap libssl-dev parted \
    live-build linaro-image-tools \
    apt-utils automake bc binfmt-support bison ca-certificates \
    cmake crossbuild-essential-arm64 \
    devscripts dh-exec dh-make dpkg-dev fakeroot gdisk git libncurses5 \
    libncurses5-dev locales pkg-config pv python python3-dev python-dev \
    swig udev apt-transport-https eatmydata e2fsprogs

RUN curl -L https://github.com/aktau/github-release/releases/download/v0.7.2/linux-amd64-github-release.tar.bz2 | tar -C /tmp -jx && \
    mv /tmp/bin/linux/amd64/github-release /usr/local/bin/

RUN wget -4 https://releases.linaro.org/components/toolchain/binaries/7.3-2018.05/aarch64-linux-gnu/gcc-linaro-7.3.1-2018.05-x86_64_aarch64-linux-gnu.tar.xz && \
	tar -xvJf gcc-linaro-7.3.1-2018.05-x86_64_aarch64-linux-gnu.tar.xz -C /usr/local && rm gcc-linaro-7.3.1-2018.05-x86_64_aarch64-linux-gnu.tar.xz

ENV USER=root \
    HOME=/root

