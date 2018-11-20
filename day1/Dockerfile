FROM alpine
RUN apk update && apk add --no-cache openssh && \
    sed -i '/\#PermitRootLogin/a\PermitRootLogin yes' /etc/ssh/sshd_config && \
    /usr/bin/ssh-keygen -A 
COPY shadow  /etc/
EXPOSE 22 
CMD ["/usr/sbin/sshd","-D"]
