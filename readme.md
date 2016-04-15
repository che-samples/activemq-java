# activemq-java

ActiveMQ Sample Application

# Developer Workspace
[![Contribute](http://beta.codenvy.com/factory/resources/codenvy-contribute.svg)](http://beta.codenvy.com/f?id=pd06i74cp29xxfnh)

# Custom Stack 

FROM [codenvy/ubuntu_jdk8](https://hub.docker.com/r/codenvy/ubuntu_jdk8/)

RUN cd /home/user && wget -q http://apache.volia.net/activemq/5.13.2/apache-activemq-5.13.2-bin.tar.gz && tar -xvf apache-activemq-5.13.2-bin.tar.gz

EXPOSE 8161

# How to run

1. ActiveMQ is started automaticaly when a workspace starts. Click the Preview URL, login to ActiveMQ web console with the default credentials `admin/admin`. Go to Subscribers tab. There are no subscribers there. Let's add one.
2. Run `build` command in the CMD widget.
3. Start Listener with `start-listener` command. Go to ActiveMQ web console to find a new Subscriber (refresh the tab).
4. Finaly, start Publisher with `start-publisher` command.

| #       | Description           | Command  |
| :------------- |:-------------| :-----|
| 1      | Run ActiveMQ | `/home/user/apache-activemq-5.13.2/bin/activemq console` |
| 2      | Build | `mvn install` |
| 3      | Start Listener | `java -cp ${current.project.path}/target/amqp-example-0.1-SNAPSHOT.jar example.Listener` |
| 4      | Start Publisher | `java -cp ${current.project.path}/target/amqp-example-0.1-SNAPSHOT.jar example.Publisher` |
