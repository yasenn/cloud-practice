# Deployment

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

