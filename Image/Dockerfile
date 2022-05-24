FROM tomcat:alpine
WORKDIR /usr/local/tomcat

# Copy war application to dest
ADD sample.war ./webapps/

# Copy jmx agent and conf file to tomcat bin
ADD jmx_prometheus_javaagent_java6-0.16.1.jar ./bin/
ADD myconf.yml ./bin/

# sh script to add JMX agent to CATALINA_OPTS
ADD setenv.sh ./bin/

# Exposed ports
EXPOSE 8080
EXPOSE 9100
EXPOSE 3100

CMD ["catalina.sh", "run"]