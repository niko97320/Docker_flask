FROM ubuntu:16.04
MAINTAINER florian.pereme@altran.com

RUN apt-get update  && apt-get install -y python3-pip python3-dev openssh-server git
RUN cd /usr/local/bin && ln -s /usr/bin/python3 python 
RUN pip3 install --upgrade pip 


RUN pip3 install 'flask == 0.12.4' 'bokeh == 0.12.5' numpy pandas



 
  
RUN mkdir -p /var/run/sshd
RUN echo 'root:medica' | chpasswd
RUN sed -ri 's/^PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config


EXPOSE 5000 50006 80 8080 8082 22
CMD /usr/sbin/sshd -D
