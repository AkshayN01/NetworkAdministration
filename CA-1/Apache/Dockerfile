# Use the CentOS 7 base image
FROM centos:7


# Install Apache HTTP Server
RUN yum install -y httpd


# Expose port 80 for web traffic
EXPOSE 80


# Start Apache service
CMD ["httpd", "-D", "FOREGROUND"]