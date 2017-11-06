FROM tomcat:7
MAINTAINER JASON LUI
EXPOSE 8080
COPY  pinpoint-agent-1.6.2.tar.gz /usr/local/tomcat/pinpoint/ 
RUN cd pinpoint && tar -xvf pinpoint-agent-1.6.2.tar.gz  && rm pinpoint-agent-1.6.2.tar.gz
COPY  catalina.sh /usr/local/tomcat/bin/
RUN  cd pinpoint; ls ;sed -i 's/127\.0\.0\.1/collector/' pinpoint.config
