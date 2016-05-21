# Ansible docker
This docker container equips you with the latest devel release of ansible
Great for testing of playbooks or roles against the upstream version


After building centos7-base and python:2.7 you can simply create the ansible docker image.

afterwards run it with
```
docker run -ti ansible -v /your-playbooks:/playbooks bash
```
or run your play directly
```
docker run -ti ansible -v /your-playbooks:/playbooks /playbooks/play.yml -vvvv
````
