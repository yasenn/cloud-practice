# E2E cloud pracice with summarizer bot

## Localhost' prerequisites

### yc
[Getting started with the command-line interface | Yandex Cloud - Documentation](https://cloud.yandex.com/en-ru/docs/cli/quickstart)

The _Yandex Cloud command-line interface (CLI)_ provides downloadable software for managing your cloud resources from the command line.

```
curl -sSL https://storage.yandexcloud.net/yandexcloud-yc/install.sh | bash
```

### yq

yq: a lightweight and portable command-line YAML processor

```
pip install yq jq
```
or
```
binenv install yq
```

## yc instance

export YC_HOST=practice

### Let's run jumphost in the cloud

```
yc compute instance create \
--name $YC_HOST \
--hostname $YC_HOST \
--cores 4 \
--memory 8GB \
--create-boot-disk image-folder-id=standard-images,image-family=ubuntu-2204-lts,size=80GB \
--network-interface subnet-name=default-ru-central1-a,nat-ip-version=ipv4 \
--ssh-key /home/$USER/.ssh/id_rsa.pub
```


### get ip 

```
export YC_JUMPHOST_IP=$(yc compute instance get $YC_HOST | yq '.network_interfaces[].primary_v4_address.one_to_one_nat.address')
```

### SSH Jump In

```
ssh -o StrictHostKeyChecking=false yc-user@${YC_JUMPHOST_IP}
```

## Jumphost' prerequisites

```
# sudo apt install python3 
curl -L https://bootstrap.pypa.io/get-pip.py | python3 -
~/.local/bin/pip3 install -r requirements.txt
```
### docker

```
curl -L https://get.docker.com | bash
sudo usermod -aG docker $USER
newgrp docker
docker ps
```

## Build bot's docker image

### git clone repo

```
git clone https://github.com/galinaalperovich/ai_summary_tg_bot
cd ai_summary_tg_bot
```

### Declare tg token

