FROM python:2.7

VOLUME ['/sources']
VOLUME ['/playbooks']
RUN yum install -y libffi-devel openssl-devel && yum clean all
RUN pip install pycrypto ansible paramiko
RUN pip install --upgrade setuptools
RUN mkdir -p /sources/modules
RUN cd /sources/modules && git clone https://github.com/ansible/ansible-modules-extras.git -b devel
RUN cd /sources/modules &&  git clone https://github.com/ansible/ansible-modules-core.git -b devel
RUN cd /sources && git clone https://github.com/ansible/ansible.git -b devel
RUN cd /sources/ansible && python ./setup.py install
ADD ansible.cfg /etc/ansible/ansible.cfg
ADD hosts /etc/ansible/hosts