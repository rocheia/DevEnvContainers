FROM  public.ecr.aws/amazonlinux/amazonlinux:2022

# Install Java 17 JDK
RUN yum install -y java-17-amazon-corretto-devel && yum clean all

# Install Maven
RUN yum install -y maven && yum clean all

# Install git
RUN yum install -y git && yum clean all

# Add local user and switch to local account (not root)
RUN yum install -y shadow-utils && yum clean all
RUN adduser dev_user
