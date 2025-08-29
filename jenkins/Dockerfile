FROM jenkins/jenkins:lts-jdk17

# Pre-install plugins
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN jenkins-plugin-cli --plugin-file /usr/share/jenkins/ref/plugins.txt

# Install Docker CLI
USER root
RUN apt-get update && apt-get install -y docker.io && rm -rf /var/lib/apt/lists/*

# Preconfigure Maven Global Settings directory
RUN mkdir -p /var/maven/repo && chown -R jenkins:jenkins /var/maven/repo

# Switch back to Jenkins user
USER jenkins

