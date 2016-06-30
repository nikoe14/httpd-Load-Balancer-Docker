# Small Architecture using 2 nodes and 1 Load Balancer
  - Load Balancer: Nginx
  - Nodes: Apache
  
### Version
0.1
### Architecture
![Alt text](http://i.imgur.com/4LhHkaz.png "Small Architecture")

### How to run this on your computer? 

You need to have installed Docker and Docker-compose, on the Web page you have the steps for do that, I will leave here the links.

  - [Ubuntu](https://docs.docker.com/engine/installation/linux/ubuntulinux/)
  - [MAC OS X](https://docs.docker.com/engine/installation/mac/)
  - [Windows](https://docs.docker.com/engine/installation/windows/)
  
If you have other OS click [here](https://docs.docker.com/engine/installation/).

After Docker instalation clone this repository.

```
git clone https://github.com/nikoe14/https-Load-Balancer-Docker.git
```
You will see the following directory structure.

### Directories Structure

```
/https-Load-Balancer-Docker/

	├── httpd_custom
	│
	├── nginx_custom
	│
	├── docker-compose.yml
	│
	└── README.mb
```
Then open a terminal and do the following.
```
cd https-Load-Balancer-Docker 
```
```
docker-compose up 
```