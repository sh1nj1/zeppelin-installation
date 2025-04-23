# Zeppelin Installation

- This is Apache Zeppelin installation directory to use pre-configured Zeppelin by cloning this repo.

## Install

### Install JDK

AWS Amazon Linux

```bash
sudo yum install java-21-amazon-corretto-headless -y
```

### Install Zeppelin

- clone this repository
- change environment variables

open conf/zeppelin-env.sh and change

```bash
export ZEPPELIN_ADDR=0.0.0.0
export ZEPPELIN_PORT=8099
```

- install Zeppelin binary

```bash
wget https://downloads.apache.org/zeppelin/zeppelin-0.12.0/zeppelin-0.12.0-bin-all.tgz
tar xvfz zeppelin-0.12.0-bin-all.tgz
ln -sf zeppelin-0.12.0-bin-all default
```

- configure conf dir

```bash
mv ./default/conf ./default/conf-origin
ln -sf ${PWD}/conf ./default/conf
```

- register system service

```bash
sudo ./default/bin/zeppelin-systemd-service.sh enable
```
