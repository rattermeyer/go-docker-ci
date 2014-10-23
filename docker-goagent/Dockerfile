FROM rattermeyer/ubuntu-jdk:1.0
MAINTAINER Patrick M�ller "patrick-mueller@gmx.net"

#RUN rm -fR /var/lib/apt/lists/*
RUN apt-get update
RUN apt-get upgrade -y --force-yes
RUN apt-get install wget
RUN apt-get install unzip
RUN wget http://download.go.cd/gocd-deb/go-agent-14.2.0-377.deb -O /tmp/go-agent.deb
RUN dpkg -i /tmp/go-agent.deb
# Go Agent Ports?
#EXPOSE 8153 8154
# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
# Start Go Agent, create go-agent logfile and tail it
CMD /etc/init.d/go-agent start && > /var/log/go-agent/go-agent.log && tail -F /var/log/go-agent/go-agent.log