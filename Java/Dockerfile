FROM  public.ecr.aws/amazonlinux/amazonlinux:2022

# Install Java 17 JDK
RUN yum install -y java-17-amazon-corretto-devel && yum clean all

# Install Maven
RUN yum install -y maven && yum clean all

# Install git
RUN yum install -y git && yum clean all

# Add local user
RUN  addgroup -S dev_group && adduser -S dev_user -G dev_group

# Switch to dev_user 
USER dev_user
