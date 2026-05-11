FROM jenkins/jenkins:lts

# Switch to root user to install software
USER root

# Update the package list and install vim and nano
RUN apt-get update && apt-get install -y vim nano

# Switch back to the jenkins user for security
USER jenkins

# Skip the setup wizard
ENV JAVA_OPTS="-Djenkins.install.runSetupWizard=false"

# Install plugins
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN jenkins-plugin-cli --plugin-file /usr/share/jenkins/ref/plugins.txt