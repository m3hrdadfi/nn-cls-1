# Get Docker CE for Ubuntu
> ocker is a software technology providing containers, promoted by the company Docker, Inc. Docker provides an additional layer of abstraction and automation of operating-system-level virtualization on Windows and Linux.

## OS requirements
To install Docker CE, you need the 64-bit version of one of these Ubuntu versions:

- Artful 17.10 (Docker CE 17.11 Edge only)
- Zesty 17.04
- Xenial 16.04 (LTS)
- Trusty 14.04 (LTS)


### TRUSTY 14.04
Unless you have a strong reason not to, install the `linux-image-extra-*` packages, which allow Docker to use the `aufs` storage drivers.

```
$ sudo apt-get update

$ sudo apt-get install \
    linux-image-extra-$(uname -r) \
    linux-image-extra-virtual
```    

## Install Docker CE
Update the `apt` package index:

```
$ sudo apt-get update
```

Install packages to allow `apt` to use a repository over HTTPS:

```
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
```

Add Docker’s official GPG key:

```
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

Use the following command to set up the **stable** repository. You always need the **stable** repository, even if you want to install builds from the **edge** or **test** repositories as well. To add the edge or test repository, add the word `edge` or `test` (or both) after the word `stable` in the commands below.

```
lsb_release -cs
lscpu
```

amd64:

```
$ sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```   

armhf:

```
$ sudo add-apt-repository \
   "deb [arch=armhf] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```
   
s390x:

```
$ sudo add-apt-repository \
   "deb [arch=s390x] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```   


## INSTALL DOCKER CE
Update the apt package index.

```
$ sudo apt-get update
```

Install the latest version of Docker CE, or go to the next step to install a specific version. Any existing installation of Docker is replaced.

```
$ sudo apt-get install docker-ce
```

On production systems, you should install a specific version of Docker CE instead of always using the latest. This output is truncated. List the available versions.

```
$ apt-cache madison docker-ce
```

Verify that Docker CE is installed correctly by running the `hello-world` image.

```
sudo docker run hello-world
```