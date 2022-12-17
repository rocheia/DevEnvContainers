FROM  public.ecr.aws/amazonlinux/amazonlinux:2022

# Install Java 17 JDK
RUN yum install -y java-17-amazon-corretto-devel && yum clean -all

# Install Maven
RUN yum install -y maven && yum clean -all
