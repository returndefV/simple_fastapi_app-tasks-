## FastAPI - Small web-app for scheduling tasks

## Creating a repository
```
git init
git remote add origin git@github.com:<username>/<repositoryname>.git
.... add gitignore
git add .
git commit -m "..."
git branch -M main
git push -u origin main
```

## Server preparation
### git
```
sudo apt-get update
sudo apt-get install git
```

### docker
You can use the instructions: https://docs.docker.com/engine/install/ubuntu/
or copy the code below
```
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### Launching a web-app
Creating an image with the application
```
docker build . --tag fastapi_app
```
Running an image in a container with port forwarding to access the container from the Internet
```
docker run -p 80:80 fastapi_app
```
