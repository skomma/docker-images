FROM skomma/trusty-oraclejdk7
MAINTAINER Syunsuke Komma <syunsuke@weseek.co.jp>

## Install Jenkins
RUN wget -q -O - http://pkg.jenkins-ci.org/debian/jenkins-ci.org.key | apt-key add -
RUN echo 'deb http://pkg.jenkins-ci.org/debian binary/' > /etc/apt/sources.list.d/jenkins.list
RUN apt-get update
RUN apt-get install -y jenkins

## Install supervisord configuration file
ADD src/supervisord-jenkins.conf /etc/supervisord/conf.d/jenkins.conf

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*


EXPOSE 8080
