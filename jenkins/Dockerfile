FROM ubuntu:latest

# Install dependencies
RUN apt-get update && apt-get install -y \
    openjdk-17-jdk \
    wget \
    git \
    && rm -rf /var/lib/apt/lists/*

# Add Jenkins user
RUN useradd -m -d /var/jenkins_home -s /bin/bash jenkins \
    && mkdir -p /var/jenkins_home \
    && chown -R jenkins:jenkins /var/jenkins_home

# Set environment variables
ENV JENKINS_HOME /var/jenkins_home

# Download Jenkins
RUN wget -q -O /usr/share/jenkins.war https://get.jenkins.io/war-stable/latest/jenkins.war

# Expose ports
EXPOSE 8080 50000

# Start Jenkins
USER jenkins
CMD ["java", "-jar", "/usr/share/jenkins.war"]
