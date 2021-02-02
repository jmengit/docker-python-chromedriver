# docker-python-chromedriver

Super simple container to run basic basic python scripts that require chromedriver and selenium.

### Simple Build and Run:
The entrypoint for the docker is a bash shell. By default the container will run a script called "main.sh" in the "/scripts" folder. If this is what you want, simply map the folder that contains your scripts on your host drive to "/scripts"
```
docker build -t python-chromedriver https://raw.githubusercontent.com/jmengit/docker-python-chromedriver/main/Dockerfile
docker run -v "/script/directory/on/host:/scripts" python-chromedriver
```

### Docker-Compose YAML Example
```
version: "3.8"
services:
  python-chromedriver:
    image: jmendock/python-chromedriver
    container_name: python-chromedriver
    restart: unless-stopped
    volumes:
      - /script/directory/on/host:/scripts
```      
