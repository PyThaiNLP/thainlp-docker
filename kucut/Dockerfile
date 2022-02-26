# Python 2.6 from https://gist.github.com/mjhea0/03fdaa4ff1e0311d7651e6a815d01583
# base image
FROM mjhea0/centos-6-python-2.6:latest

RUN git clone https://github.com/Thanabhat/KUCut.git

WORKDIR "/KUCut"

RUN python setup.py install