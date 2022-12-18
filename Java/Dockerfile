FROM redhat/ubi8

######################
# Container for building Java libraries includes:
#
# Maven
# Open JDK 17
# Docker
#

# Create Tools directory
RUN mkdir /tools
# Install Maven
WORKDIR /tools

# Install Java 17 JDK
RUN curl https://download.java.net/java/GA/jdk17.0.2/dfd4a8d0985749f896bed50d7138ee7f/8/GPL/openjdk-17.0.2_linux-x64_bin.tar.gz -o openjdk.tar.gz
RUN tar -xvzf openjdk.tar.gz && rm openjdk.tar.gz
ENV JAVA_HOME=/tools/jdk-17.0.2
ENV PATH=$JAVA_HOME/bin:$PATH

# Install Maven 3.8.6
RUN curl https://dlcdn.apache.org/maven/maven-3/3.8.6/binaries/apache-maven-3.8.6-bin.tar.gz -o maven.tar.gz
RUN tar -xvzf maven.tar.gz && rm maven.tar.gz
ENV M2_HOME=/tools/apache-maven-3.8.6
ENV M2=$M2_HOME/bin
ENV PATH=$M2:$PATH

WORKDIR /

# Install git
RUN yum install -y git && yum clean all

# Install Docker
COPY docker.repo /etc/yum.repos.d/
RUN yum install -y docker-ce --nobest && yum clean all

# Add local user and switch to local account (not root)
RUN groupadd --gid 1000 devuser && useradd --uid 1000 --gid 1000 -m devuser
ENV HOME /home/devuser

# Create workspaces directory
RUN mkdir /workspaces && chown devuser:devuser /workspaces

USER devuser
