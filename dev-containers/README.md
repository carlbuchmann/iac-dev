# Docker Containers for Ansible Testing and Development

The docker container approach for development can be used to ensure that
everybody is using the same development environment while still being flexible
enough to use the repo you are making changes in. You can inspect the
Dockerfile to see what packages have been installed.

The ansible version is passed in with the docker build command using
***ANSIBLE*** variable.  If the ***ANSIBLE*** variable is not used the
Dockerfile will by default set the ansible version to 2.9.2

Dockerfiles are available for the following platforms:

- Centos 7 Python 2.7   -> PLATFORM=centos7-py2
- Centos 7 Python 3.6.8 -> PLATFORM=centos7-py3
- Centos 8 Python 3.6.8 -> PLATFORM=centos8

```bash
docker build -f -f ./docker/<platform>/Dockerfile -t ansible_avd . --build-arg UID=$(id -u) --build-arg GID=$(id -g) --build-arg ANSIBLE=<ansible version>
```

Start up the docker container from the root of the repo directory with the
following command. Note that specifying the -u option allows you to run the
container as your user-id and not as root. This eliminates problem with
creating files owned by root in your repo.

```bash
docker run -t -d --name ansible_avd -v $(pwd)/:/ansible_avd -v /etc/hosts:/etc/hosts ansible_avd
```

Use docker exec to login into the container with a bash shell.

```bash
docker exec -it ansible_avd bash
```

In addition to using docker commands to start up and access the container, make can be used to do
this in a single step.  A user can pass the ansible version number to make and alter the default
ansible-version number.  This allows a user to setup multiple containers running differing
versions of ansible.

```bash
make PLATFORM=centos8           # Use default version of Ansible w/Centos8
make PLATFORM=centos8 ANSIBLE_VERSION=2.9.1  # Explicitly set Ansible version to 2.9.1 w/Centos8

docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
a9d97c5a6f6c        ansible_avd:2.9.2   "/bin/sh"           7 seconds ago       Up 7 seconds                            ansible_avd_2.9.2_centos8
1ade94d62032        ansible_avd:2.9.1   "/bin/sh"           54 seconds ago      Up 53 seconds                           ansible_avd_2.9.1_centos8
```

Another make target (clean) has been created to stop and remove the container once the user
is finished with it.

```bash
make PLATFORM=centos8 clean        #  clean default version of Ansible w/Centos8
make PLATFORM=centos8 ANSIBLE_VERSION=2.9.1  clean # Explicitly clean Ansible version to 2.9.1 w/Centos8

docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
```
