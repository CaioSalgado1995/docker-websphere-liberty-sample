FROM websphere-liberty

ADD docker/server.xml /opt/ibm/wlp/usr/servers/defaultServer/
ADD docker/server.env /opt/ibm/wlp/usr/servers/defaultServer/
ADD target/bgs-hello-world.war /opt/ibm/wlp/usr/servers/defaultServer/dropins/

RUN installUtility install --acceptLicense microProfile-3.0

ENTRYPOINT ["/opt/ibm/wlp/bin/server", "run", "defaultServer"]