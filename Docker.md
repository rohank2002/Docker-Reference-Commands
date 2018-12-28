Docker on EC2_AWS_Installation
```sh
sudo yum update -y 
sudo yum install -y docker 
sudo service docker start
sudo usermod -a -G docker ec2-user
```
Portainer Service 
```sh
docker volume create portainer_data
docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer
```
Create Network:
```sh
sudo docker network create --driver bridge gumball
```
Delete Network
```
docker network rm gumball
```

List of networks
```sh
sudo docker network ls
```
Delete Container
```sh
docker ps -a
docker rm
```
Network Connect
```sh
docker network connect
docker network connect mongodb_network 0d0ad4c6404a
```
Check running docker containers
```sh
docker ps --all --format "table {{.ID}}\t{{.Names}}\t{{.Image}}\t{{.Status}}\t"
```
Check used ports
```sh
docker ps --all --format "table {{.Names}}\t{{.Ports}}\t"
```
