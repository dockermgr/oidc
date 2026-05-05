## 👋 Welcome to oidc 🚀  

oidc README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update oidc
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/oidc/volumes"
git clone "https://github.com/dockermgr/oidc" "$HOME/.local/share/CasjaysDev/dockermgr/oidc"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/oidc/volumes/." "$HOME/.local/share/srv/docker/oidc/volumes/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-oidc \
--hostname oidc \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-oidc/volumes/data:/data:z" \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-oidc/volumes/config:/config:z" \
-p 80:80 \
casjaysdevdocker/oidc:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/oidc
    container_name: casjaysdevdocker-oidc
    environment:
      - TZ=America/New_York
      - HOSTNAME=oidc
    volumes:
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-oidc/volumes/data:/data:z"
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-oidc/volumes/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/oidc
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/oidc" "$HOME/Projects/github/casjaysdevdocker/oidc"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/oidc"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
