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
git clone 
```
You will see the following directory structure.

### Directories Structure

```
/project-folder/
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
cd project-folder 
```
```
docker-compose up 
```

After that open other terminal and execute the following command
```
docker ps
```
You will see this
```
nico@nico-desktop:~/Documents/Facultad$ docker ps
CONTAINER ID        IMAGE                          COMMAND                  CREATED             STATUS              PORTS               NAMES
6b1167ff831a        nginx_custom                   "nginx -g 'daemon off"   About an hour ago   Up About an hour    80/tcp, 443/tcp     Load_Balancer_nginx
158cfebe7257        nikoe14/httpd-container-info   "/entrypoint.sh"         About an hour ago   Up About an hour    80/tcp              container2.com
46fa3e613a9f        nikoe14/httpd-container-info   "/entrypoint.sh"         About an hour ago   Up About an hour    80/tcp              container1.com
```
Those are the three containers, the load balancer and the other two nodes.
You need know the load balancer ip so you will execute the next command.

```
docker inspect CONTAINER-ID | grep IPAddress
```
In this case

```
nico@nico-desktop:~/Documents/Facultad$ docker inspect 6b1167ff831a | grep IPAddress
            "SecondaryIPAddresses": null,
            "IPAddress": "",
                    "IPAddress": "172.19.0.4",
```
Copy the IP and paste in a browser, when you refresh the web site you will see that the content of the page changes.

![Alt text](http://i.imgur.com/UJv6BWK.png "Web")
![Alt text](http://i.imgur.com/XcPohIS.png "Web")

