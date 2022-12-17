FROM  public.ecr.aws/amazonlinux/amazonlinux:2022

# Install Java 17 JDK
RUN yum install -y java-17-amazon-corretto-devel && yum clean all

# Install Maven
RUN yum install -y maven && yum clean all

# Install git
RUN yum install -y git && yum clean all

# Add local user and switch to local account (not root)
RUN groupadd vscode -g 1000
RUN useradd -g 1000 -u 1000 vscode
ENV HOME /home/vscode
