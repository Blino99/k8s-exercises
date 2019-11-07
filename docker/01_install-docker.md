# Install Docker
In this course we will install Docker to a Debian machine.

1. Install some necessary packages upfront
```bash
sudo apt install -y \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg2 \
    software-properties-common \
    bash-completion
```
2. Add Docker’s official GPG key:
```bash
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
```
3. Setup the Docker Repository
```bash
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/debian \
   $(lsb_release -cs) \
   stable"
```
4. Update the package index
```bash
sudo apt update 
```
5. Install the latest version of Docker
```bash
sudo apt install docker-ce docker-ce-cli containerd.io -y
```
6. Add your user to the group `docker`. Note that you have to logout and login to your terminal for this to take effect.
```bash
sudo usermod -aG docker <USER>
```
7. Add docker bash completion. Note that you have to logout and login to your terminal for this to take effect.
```bash
sudo curl https://raw.githubusercontent.com/docker/docker-ce/master/components/cli/contrib/completion/bash/docker -o /etc/bash_completion.d/docker.sh
```
8. Verify your installation
```bash
docker -v
```
9. Run a Container
```bash
docker run -it busybox echo hello docker
```
10. See details of your Container
```bash
docker ps -a
```
11. Remove the Container
```bash
docker rm <CONTAINER-NAME>
```