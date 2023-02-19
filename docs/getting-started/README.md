# Quick Start Guide

## Linux Kernel Requirement

### Kernel Version

Use `uname -r` to check the kernel version on your machine.

> **Notes**
> If you find your kernel version is `< 5.8`, follow the guide [HERE](./kernel-upgrade.md) to upgrade the kernel to the minimum required version.

## Usage

### Build

**Make Dependencies**

```shell
clang >= 10
llvm >= 10
golang >= 1.18
make
```

**Build**

```shell
git clone https://github.com/v2rayA/dae.git
cd dae
git submodule update --init
# Minimal dependency build:
make GOFLAGS="-buildvcs=false" CC=clang
# Or normal build:
# make
```

### Run

**Runtime Dependencies**

Download [geoip.dat](https://github.com/v2ray/geoip/releases/latest) and [geosite.dat](https://github.com/v2fly/domain-list-community/releases/latest) to `/usr/local/share/dae/`.

```
mkdir -p /usr/local/share/dae/
pushd /usr/local/share/dae/
curl -L -o geoip.dat https://github.com/v2ray/geoip/releases/latest/download/geoip.dat
curl -L -o geosite.dat https://github.com/v2ray/domain-list-community/releases/latest/download/dlc.dat
popd
```

**Run**

```shell
./dae run -c example.dae
```

See [example.dae](https://github.com/v2rayA/dae/blob/main/example.dae).