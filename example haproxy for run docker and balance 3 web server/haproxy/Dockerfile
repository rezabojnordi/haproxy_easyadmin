FROM ubuntu:18.04

# Create a system group and user to be used by HAProxy.
#RUN groupadd haproxy && useradd -g haproxy haproxy
RUN  apt update && apt install vim -y && apt install haproxy -y
# Need to create a directory for HAProxy to be able to `chroot`.
# This is a security measurement.
# Refer to http://cbonte.github.io/haproxy-dconv/configuration-1.5.html#chroot.
#RUN mkdir /var/lib/haproxy
WORKDIR /usr/local/etc/haproxy/
# Now copy the configurations file applicable for NELO2.
COPY haproxy.cfg haproxy.cfg


CMD ["tail -f /var/log/syslog"]
